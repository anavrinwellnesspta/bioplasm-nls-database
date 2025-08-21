<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bioplasm NLS V6 Medical Database</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        body { font-family: 'Inter', sans-serif; }
        .gradient-bg { background: linear-gradient(135deg, #1e40af 0%, #3730a3 50%, #581c87 100%); }
        .condition-card { transition: all 0.3s ease; cursor: pointer; }
        .condition-card:hover { transform: translateY(-2px); box-shadow: 0 10px 25px rgba(0, 0, 0, 0.15); }
    </style>
</head>
<body class="bg-gray-50">
    <!-- Header -->
    <header class="gradient-bg text-white shadow-lg">
        <div class="container mx-auto px-6 py-4">
            <div class="flex items-center justify-between">
                <div class="flex items-center space-x-4">
                    <div class="text-3xl">🔬</div>
                    <div>
                        <h1 class="text-2xl font-bold">Bioplasm NLS V6 Database</h1>
                        <p class="text-blue-100 text-sm">Anavrin Wellness - Medical Conditions Protocol</p>
                    </div>
                </div>
                <div class="text-right">
                    <div class="text-sm text-blue-100">Total Conditions</div>
                    <div class="text-xl font-bold" id="totalCount">Loading...</div>
                </div>
            </div>
        </div>
    </header>

    <!-- Search Section -->
    <div class="bg-white shadow-sm border-b">
        <div class="container mx-auto px-6 py-4">
            <div class="flex flex-col lg:flex-row gap-4 items-center">
                <div class="flex-1 relative">
                    <input type="text" id="searchInput" placeholder="Search medical conditions..." 
                           class="w-full pl-12 pr-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500">
                    <div class="absolute left-4 top-1/2 transform -translate-y-1/2 text-gray-400">
                        <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path>
                        </svg>
                    </div>
                </div>
                <select id="systemFilter" class="px-4 py-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500">
                    <option value="">All Systems</option>
                    <option value="cardiovascular">Cardiovascular System</option>
                    <option value="respiratory">Respiratory System</option>
                    <option value="digestive">Digestive System</option>
                    <option value="neurological">Neurology & CNS</option>
                    <option value="endocrine">Endocrine System</option>
                    <option value="renal">Renal & Urinary</option>
                    <option value="musculoskeletal">Musculoskeletal</option>
                    <option value="dermatology">Dermatology</option>
                </select>
            </div>
        </div>
    </div>

    <!-- Main Content -->
    <main class="container mx-auto px-6 py-8">
        <div class="mb-6">
            <div class="text-gray-600">
                Showing <span id="resultCount" class="font-semibold text-blue-600">0</span> conditions
            </div>
        </div>

        <!-- Conditions Grid -->
        <div id="conditionsGrid" class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 gap-6">
            <!-- Conditions will be populated here -->
        </div>
    </main>

    <!-- Modal -->
    <div id="conditionModal" class="fixed inset-0 bg-black bg-opacity-50 hidden z-50">
        <div class="flex items-center justify-center min-h-screen p-4">
            <div class="bg-white rounded-2xl max-w-4xl w-full max-h-[90vh] overflow-y-auto">
                <div class="sticky top-0 bg-white border-b px-6 py-4 flex items-center justify-between">
                    <h2 id="modalTitle" class="text-2xl font-bold text-gray-800"></h2>
                    <button id="closeModal" class="text-gray-400 hover:text-gray-600 text-2xl">×</button>
                </div>
                <div class="p-6" id="modalContent"></div>
            </div>
        </div>
    </div>

    <script>
        // Medical Conditions Database
        const medicalConditions = [
            // Cardiovascular System
            {
                name: "Hypertension",
                category: "cardiovascular",
                systems: ["Cardiovascular System"],
                whatItIs: "Hypertension is a chronic condition characterized by persistently elevated blood pressure (≥140/90 mmHg). It's often called the 'silent killer' as it typically presents without symptoms until complications develop.",
                howItAffects: "Causes headaches, dizziness, chest pain, and shortness of breath. Long-term complications include heart disease, stroke, kidney damage, and retinal damage. Can lead to heart failure and arterial damage.",
                etalons: {
                    primaryOrgan: ["Heart", "Arteries", "Kidneys", "Adrenal glands"],
                    pathomorphology: ["Arterial wall thickening", "Atherosclerotic plaques", "Left ventricular hypertrophy"],
                    associatedSystems: ["Nervous system", "Endocrine system", "Renal system"],
                    biochemical: ["Renin-angiotensin system", "Aldosterone", "Catecholamines", "Nitric oxide"]
                },
                energeticMarkers: {
                    flendlerScale: "Brown diamonds in cardiovascular etalons indicate chronic energetic stress. Red triangles suggest acute vascular tension. Black squares indicate severe energetic depletion.",
                    graphNumbers: "Numbers 4-5 in arterial etalons indicate significant energetic deviation from normal vascular tone.",
                    anabolismCatabolism: "Red catabolism lines predominant in vascular smooth muscle, indicating breakdown processes. Blue anabolism reduced in arterial repair mechanisms.",
                    isoline: "Chronic process range 0.3-0.6, acute hypertensive episodes 0.7-0.9",
                    kccValues: "KCC < 0.425 for pathological vascular etalons indicates high similarity to hypertensive patterns. Healthy arterial etalons show KCC > 0.7",
                    entropyAnalysis: "E values 4-6 in pathomorphology etalons indicate mature hypertensive changes",
                    biochemicalHomeostasis: "E values 1 or 7 in renin-angiotensin etalons indicate significant deviation",
                    vegetativeTest: "+10% or more strengthening with antihypertensive preparations indicates energetic compatibility"
                },
                protocol: {
                    initialScan: "Complete cardiovascular system scan with focus on arterial tree and cardiac function",
                    focusedAnalysis: "Detailed analysis of arterial wall etalons, cardiac output patterns, and renal function markers",
                    metaTherapy: {
                        selection: "Select arterial wall etalons with highest energetic stress (lowest KCC values)",
                        settings: "Level 3-4, Therapy mode, 15-20 minutes per session",
                        sessions: "2-3 sessions per week, monitor blood pressure changes after each session",
                        focus: "Maximum 3-4 etalons per session to avoid energetic overload"
                    },
                    vegetativeTest: "Test energetic compatibility with cardiovascular support preparations",
                    imprinting: "Transfer beneficial frequencies onto water (drink 3x daily) or sugar pellets (3 pellets 3x daily). Duration: 2-3 weeks per imprinting cycle"
                },
                steps: [
                    "Initial comprehensive cardiovascular scan",
                    "Analysis of arterial walls and blood flow patterns",
                    "Meta-therapy on highest stress arterial etalons",
                    "Vegetative testing of cardiovascular preparations",
                    "Frequency imprinting and follow-up assessment"
                ],
                targets: ["Arterial walls", "Smooth muscle cells", "Kidneys", "Adrenal glands"],
                notes: [
                    "CRITICAL: Ongoing medical monitoring essential - never discontinue prescribed medications",
                    "Monitor blood pressure before and after each session",
                    "Coordinate with cardiologist for medication adjustments",
                    "Regular energetic follow-up every 2-3 weeks recommended"
                ]
            },
            {
                name: "Coronary Artery Disease",
                category: "cardiovascular",
                systems: ["Cardiovascular System"],
                steps: [
                    "Comprehensive cardiac scan with coronary focus",
                    "Analysis of coronary circulation and blockages",
                    "Frequency therapy for arterial patency",
                    "Meta-therapy with cardiac support preparations",
                    "Assessment of cardiac function improvement"
                ],
                targets: ["Coronary arteries", "Myocardium", "Cardiac conduction system"],
                notes: [
                    "Contraindicated in acute MI",
                    "Monitor cardiac enzymes",
                    "Regular cardiology follow-up recommended"
                ]
            },
            {
                name: "Atrial Fibrillation",
                category: "cardiovascular",
                systems: ["Cardiovascular System"],
                steps: [
                    "Cardiac rhythm analysis scan",
                    "Focus on atrial conduction pathways",
                    "Rhythm stabilization frequencies",
                    "Meta-therapy for cardiac rhythm support",
                    "Post-treatment rhythm assessment"
                ],
                targets: ["Sinoatrial node", "Atrioventricular node", "Atrial muscle"],
                notes: [
                    "Monitor for stroke risk",
                    "Check anticoagulation status",
                    "Coordinate with cardiologist"
                ]
            },

            // Respiratory System
            {
                name: "Asthma",
                category: "respiratory",
                systems: ["Respiratory System"],
                steps: [
                    "Comprehensive respiratory system scan",
                    "Analysis of bronchial reactivity and inflammation",
                    "Anti-inflammatory frequency therapy",
                    "Meta-therapy with respiratory support preparations",
                    "Lung function reassessment"
                ],
                targets: ["Bronchioles", "Alveoli", "Respiratory epithelium", "Smooth muscle"],
                notes: [
                    "Monitor peak flow measurements",
                    "Identify and avoid triggers",
                    "Emergency inhaler always available"
                ]
            },
            {
                name: "COPD",
                category: "respiratory",
                systems: ["Respiratory System"],
                steps: [
                    "Detailed pulmonary function scan",
                    "Assessment of airway obstruction and emphysema",
                    "Bronchodilation support frequencies",
                    "Meta-therapy for lung tissue repair",
                    "Respiratory capacity evaluation"
                ],
                targets: ["Alveolar walls", "Bronchi", "Respiratory muscles"],
                notes: [
                    "Smoking cessation essential",
                    "Monitor oxygen saturation",
                    "Pulmonary rehabilitation support"
                ]
            },
            {
                name: "Pneumonia",
                category: "respiratory",
                systems: ["Respiratory System"],
                steps: [
                    "Lung infection assessment scan",
                    "Identification of affected lung segments",
                    "Anti-infectious frequency therapy",
                    "Meta-therapy with immune support preparations",
                    "Resolution monitoring scan"
                ],
                targets: ["Alveoli", "Bronchi", "Lung parenchyma", "Immune cells"],
                notes: [
                    "Monitor vital signs closely",
                    "Hydration and rest important",
                    "Complete antibiotic course if prescribed"
                ]
            },

            // Digestive System
            {
                name: "Gastritis",
                category: "digestive",
                systems: ["Digestive System"],
                steps: [
                    "Gastric mucosa assessment scan",
                    "Analysis of inflammation and acid production",
                    "Gastric healing frequency therapy",
                    "Meta-therapy with gastric protection preparations",
                    "Mucosal healing evaluation"
                ],
                targets: ["Gastric mucosa", "Parietal cells", "Chief cells"],
                notes: [
                    "Avoid NSAIDs and alcohol",
                    "Small frequent meals recommended",
                    "Stress management important"
                ]
            },
            {
                name: "GERD",
                category: "digestive",
                systems: ["Digestive System"],
                steps: [
                    "Esophageal function assessment",
                    "Analysis of acid reflux and mucosal damage",
                    "Esophageal healing frequency therapy",
                    "Meta-therapy with acid neutralization preparations",
                    "Reflux symptom improvement evaluation"
                ],
                targets: ["Lower esophageal sphincter", "Esophageal mucosa", "Stomach"],
                notes: [
                    "Lifestyle modifications crucial",
                    "Elevate head of bed",
                    "Avoid trigger foods"
                ]
            },
            {
                name: "IBS",
                category: "digestive",
                systems: ["Digestive System"],
                steps: [
                    "Comprehensive bowel function scan",
                    "Analysis of motility and sensitivity patterns",
                    "Gut-brain axis balancing frequencies",
                    "Meta-therapy with digestive harmony preparations",
                    "Symptom pattern reassessment"
                ],
                targets: ["Enteric nervous system", "Intestinal smooth muscle", "Gut microbiome"],
                notes: [
                    "Identify trigger foods",
                    "Stress management crucial",
                    "Probiotics may be beneficial"
                ]
            },

            // Neurological System
            {
                name: "Migraine",
                category: "neurological",
                systems: ["Neurology & CNS"],
                steps: [
                    "Cerebrovascular and neural pathway scan",
                    "Analysis of vascular reactivity and neural sensitization",
                    "Migraine prevention frequency therapy",
                    "Meta-therapy with neurological balance preparations",
                    "Headache pattern reassessment"
                ],
                targets: ["Trigeminal nerve", "Cerebral blood vessels", "Brainstem"],
                notes: [
                    "Identify trigger factors",
                    "Maintain headache diary",
                    "Regular sleep schedule crucial"
                ]
            },
            {
                name: "Tension Headache",
                category: "neurological",
                systems: ["Neurology & CNS"],
                steps: [
                    "Cranial muscle tension assessment",
                    "Analysis of stress and muscle contraction patterns",
                    "Muscle relaxation frequency therapy",
                    "Meta-therapy with tension relief preparations",
                    "Headache frequency reduction evaluation"
                ],
                targets: ["Scalp muscles", "Neck muscles", "Temporal muscles"],
                notes: [
                    "Stress management crucial",
                    "Regular exercise beneficial",
                    "Ergonomic workplace setup"
                ]
            },

            // Endocrine System
            {
                name: "Type 2 Diabetes",
                category: "endocrine",
                systems: ["Endocrine System"],
                steps: [
                    "Pancreatic function and glucose metabolism scan",
                    "Analysis of insulin resistance and beta-cell function",
                    "Metabolic optimization frequency therapy",
                    "Meta-therapy with glucose regulation preparations",
                    "Glycemic control assessment"
                ],
                targets: ["Pancreatic beta cells", "Insulin receptors", "Liver", "Muscle tissue"],
                notes: [
                    "Monitor blood glucose regularly",
                    "Dietary modifications essential",
                    "Regular exercise important"
                ]
            },
            {
                name: "Hypothyroidism",
                category: "endocrine",
                systems: ["Endocrine System"],
                steps: [
                    "Thyroid gland function assessment",
                    "Analysis of hormone production and metabolism",
                    "Thyroid stimulation frequency therapy",
                    "Meta-therapy with thyroid support preparations",
                    "Thyroid function evaluation"
                ],
                targets: ["Thyroid follicles", "TSH receptors", "Peripheral tissues"],
                notes: [
                    "Monitor TSH and T4 levels",
                    "Medication timing important",
                    "Lifelong monitoring required"
                ]
            },

            // Renal System
            {
                name: "Chronic Kidney Disease",
                category: "renal",
                systems: ["Renal & Urinary System"],
                steps: [
                    "Comprehensive renal function assessment",
                    "Analysis of glomerular filtration and tubular function",
                    "Nephroprotective frequency therapy",
                    "Meta-therapy with kidney support preparations",
                    "Renal function preservation evaluation"
                ],
                targets: ["Glomeruli", "Tubules", "Interstitium", "Renal blood vessels"],
                notes: [
                    "Monitor creatinine and GFR",
                    "Blood pressure control crucial",
                    "Protein restriction may be needed"
                ]
            },
            {
                name: "UTI",
                category: "renal",
                systems: ["Renal & Urinary System"],
                steps: [
                    "Urinary system infection assessment",
                    "Analysis of bacterial colonization patterns",
                    "Anti-infectious frequency therapy",
                    "Meta-therapy with urinary antiseptic preparations",
                    "Infection clearance evaluation"
                ],
                targets: ["Urothelium", "Bladder wall", "Ureters", "Urethra"],
                notes: [
                    "Increase fluid intake",
                    "Complete antibiotic course",
                    "Cranberry products may help"
                ]
            },

            // Musculoskeletal System
            {
                name: "Osteoarthritis",
                category: "musculoskeletal",
                systems: ["Musculoskeletal System"],
                steps: [
                    "Joint cartilage and bone assessment",
                    "Analysis of degenerative changes and inflammation",
                    "Cartilage regeneration frequency therapy",
                    "Meta-therapy with joint support preparations",
                    "Joint function and pain evaluation"
                ],
                targets: ["Articular cartilage", "Synovial membrane", "Subchondral bone"],
                notes: [
                    "Weight management important",
                    "Low-impact exercise beneficial",
                    "Joint protection strategies"
                ]
            },
            {
                name: "Rheumatoid Arthritis",
                category: "musculoskeletal",
                systems: ["Musculoskeletal System"],
                steps: [
                    "Autoimmune joint inflammation assessment",
                    "Analysis of synovial inflammation and bone erosion",
                    "Anti-inflammatory frequency therapy",
                    "Meta-therapy with immune modulation preparations",
                    "Disease activity evaluation"
                ],
                targets: ["Synovial membrane", "Cartilage", "Bone", "Immune cells"],
                notes: [
                    "Early aggressive treatment important",
                    "Regular rheumatologist follow-up",
                    "Biologic therapy coordination"
                ]
            },

            // Dermatology
            {
                name: "Eczema",
                category: "dermatology",
                systems: ["Dermatology"],
                steps: [
                    "Skin barrier function assessment",
                    "Analysis of inflammatory and allergic responses",
                    "Anti-inflammatory frequency therapy",
                    "Meta-therapy with skin healing preparations",
                    "Skin condition evaluation"
                ],
                targets: ["Epidermis", "Dermis", "Sebaceous glands", "Immune cells"],
                notes: [
                    "Identify and avoid triggers",
                    "Moisturization crucial",
                    "Gentle skincare products"
                ]
            },
            {
                name: "Psoriasis",
                category: "dermatology",
                systems: ["Dermatology"],
                steps: [
                    "Skin cell proliferation assessment",
                    "Analysis of autoimmune inflammation patterns",
                    "Cell cycle normalization frequency therapy",
                    "Meta-therapy with immune balance preparations",
                    "Skin lesion improvement evaluation"
                ],
                targets: ["Keratinocytes", "T-cells", "Blood vessels"],
                notes: [
                    "UV therapy may be beneficial",
                    "Stress reduction important",
                    "Monitor for joint involvement"
                ]
            }
        ];

        // Initialize the application
        let filteredConditions = [...medicalConditions];

        function updateTotalCount() {
            document.getElementById('totalCount').textContent = medicalConditions.length;
        }

        function updateResultCount() {
            document.getElementById('resultCount').textContent = filteredConditions.length;
        }

        function createConditionCard(condition) {
            const categoryColors = {
                cardiovascular: 'bg-red-100 text-red-800',
                respiratory: 'bg-blue-100 text-blue-800',
                digestive: 'bg-green-100 text-green-800',
                neurological: 'bg-purple-100 text-purple-800',
                endocrine: 'bg-yellow-100 text-yellow-800',
                renal: 'bg-indigo-100 text-indigo-800',
                musculoskeletal: 'bg-orange-100 text-orange-800',
                dermatology: 'bg-pink-100 text-pink-800'
            };

            return `
                <div class="condition-card bg-white rounded-lg shadow-md p-6 border border-gray-200" 
                     onclick="openModal('${condition.name}')">
                    <div class="flex items-start justify-between mb-3">
                        <h3 class="text-lg font-semibold text-gray-800 leading-tight">${condition.name}</h3>
                        <span class="px-2 py-1 text-xs font-medium rounded-full ${categoryColors[condition.category] || 'bg-gray-100 text-gray-800'}">
                            ${condition.category}
                        </span>
                    </div>
                    <div class="mb-3">
                        <p class="text-sm text-gray-600 mb-2">Body Systems:</p>
                        <div class="flex flex-wrap gap-1">
                            ${condition.systems.map(system => 
                                `<span class="px-2 py-1 bg-gray-100 text-gray-700 text-xs rounded">${system}</span>`
                            ).join('')}
                        </div>
                    </div>
                    <div class="mb-3">
                        <p class="text-sm text-gray-600 mb-1">Treatment Steps:</p>
                        <p class="text-xs text-gray-500">${condition.steps.length} protocol steps</p>
                    </div>
                    <div class="text-right">
                        <button class="text-blue-600 hover:text-blue-800 text-sm font-medium">
                            View Details →
                        </button>
                    </div>
                </div>
            `;
        }

        function renderConditions() {
            const grid = document.getElementById('conditionsGrid');
            if (filteredConditions.length === 0) {
                grid.innerHTML = `
                    <div class="col-span-full text-center py-12">
                        <div class="text-6xl mb-4">🔍</div>
                        <h3 class="text-xl font-semibold text-gray-800 mb-2">No conditions found</h3>
                        <p class="text-gray-600">Try adjusting your search terms or filters</p>
                    </div>
                `;
            } else {
                grid.innerHTML = filteredConditions.map(createConditionCard).join('');
            }
            updateResultCount();
        }

        function filterConditions() {
            const searchTerm = document.getElementById('searchInput').value.toLowerCase();
            const systemFilter = document.getElementById('systemFilter').value;

            filteredConditions = medicalConditions.filter(condition => {
                const matchesSearch = condition.name.toLowerCase().includes(searchTerm) ||
                                    condition.systems.some(system => system.toLowerCase().includes(searchTerm)) ||
                                    condition.targets.some(target => target.toLowerCase().includes(searchTerm));
                
                const matchesSystem = !systemFilter || condition.category === systemFilter;

                return matchesSearch && matchesSystem;
            });

            renderConditions();
        }

        function openModal(conditionName) {
            const condition = medicalConditions.find(c => c.name === conditionName);
            if (!condition) return;

            document.getElementById('modalTitle').textContent = condition.name;
            document.getElementById('modalContent').innerHTML = `
                <div class="space-y-6">
                    ${condition.whatItIs ? `
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">📋 What It Is</h3>
                        <p class="text-gray-700 bg-blue-50 p-4 rounded-lg">${condition.whatItIs}</p>
                    </div>
                    ` : ''}

                    ${condition.howItAffects ? `
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">⚠️ How It Affects the Body</h3>
                        <p class="text-gray-700 bg-red-50 p-4 rounded-lg">${condition.howItAffects}</p>
                    </div>
                    ` : ''}

                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">🎯 Body Systems Involved</h3>
                        <div class="flex flex-wrap gap-2">
                            ${condition.systems.map(system => 
                                `<span class="px-3 py-1 bg-blue-100 text-blue-800 rounded-full text-sm">${system}</span>`
                            ).join('')}
                        </div>
                    </div>

                    ${condition.etalons ? `
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">🔬 Etalons to Test</h3>
                        <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                            <div class="bg-green-50 p-4 rounded-lg">
                                <h4 class="font-medium text-green-800 mb-2">Primary Organs</h4>
                                <div class="space-y-1">
                                    ${condition.etalons.primaryOrgan.map(organ => 
                                        `<div class="text-sm text-green-700">• ${organ}</div>`
                                    ).join('')}
                                </div>
                            </div>
                            <div class="bg-purple-50 p-4 rounded-lg">
                                <h4 class="font-medium text-purple-800 mb-2">Pathomorphology</h4>
                                <div class="space-y-1">
                                    ${condition.etalons.pathomorphology.map(path => 
                                        `<div class="text-sm text-purple-700">• ${path}</div>`
                                    ).join('')}
                                </div>
                            </div>
                            <div class="bg-orange-50 p-4 rounded-lg">
                                <h4 class="font-medium text-orange-800 mb-2">Associated Systems</h4>
                                <div class="space-y-1">
                                    ${condition.etalons.associatedSystems.map(system => 
                                        `<div class="text-sm text-orange-700">• ${system}</div>`
                                    ).join('')}
                                </div>
                            </div>
                            <div class="bg-teal-50 p-4 rounded-lg">
                                <h4 class="font-medium text-teal-800 mb-2">Biochemical</h4>
                                <div class="space-y-1">
                                    ${condition.etalons.biochemical.map(bio => 
                                        `<div class="text-sm text-teal-700">• ${bio}</div>`
                                    ).join('')}
                                </div>
                            </div>
                        </div>
                    </div>
                    ` : ''}

                    ${condition.energeticMarkers ? `
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">⚡ Energetic Markers (NLS Analysis)</h3>
                        <div class="space-y-4">
                            <div class="bg-yellow-50 p-4 rounded-lg">
                                <h4 class="font-medium text-yellow-800 mb-2">Flendler's Scale Icons</h4>
                                <p class="text-sm text-yellow-700">${condition.energeticMarkers.flendlerScale}</p>
                            </div>
                            <div class="bg-indigo-50 p-4 rounded-lg">
                                <h4 class="font-medium text-indigo-800 mb-2">Graph Interpretation</h4>
                                <p class="text-sm text-indigo-700 mb-2"><strong>Numbers:</strong> ${condition.energeticMarkers.graphNumbers}</p>
                                <p class="text-sm text-indigo-700 mb-2"><strong>Anabolism/Catabolism:</strong> ${condition.energeticMarkers.anabolismCatabolism}</p>
                                <p class="text-sm text-indigo-700"><strong>Isoline:</strong> ${condition.energeticMarkers.isoline}</p>
                            </div>
                            <div class="bg-gray-50 p-4 rounded-lg">
                                <h4 class="font-medium text-gray-800 mb-2">KCC & Entropy Values</h4>
                                <p class="text-sm text-gray-700 mb-2"><strong>KCC Values:</strong> ${condition.energeticMarkers.kccValues}</p>
                                <p class="text-sm text-gray-700 mb-2"><strong>Entropy Analysis:</strong> ${condition.energeticMarkers.entropyAnalysis}</p>
                                <p class="text-sm text-gray-700"><strong>Biochemical Homeostasis:</strong> ${condition.energeticMarkers.biochemicalHomeostasis}</p>
                            </div>
                        </div>
                    </div>
                    ` : ''}

                    ${condition.protocol ? `
                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">🔧 Energetic Protocol</h3>
                        <div class="space-y-4">
                            <div class="bg-blue-50 p-4 rounded-lg">
                                <h4 class="font-medium text-blue-800 mb-2">Initial Scan</h4>
                                <p class="text-sm text-blue-700">${condition.protocol.initialScan}</p>
                            </div>
                            <div class="bg-green-50 p-4 rounded-lg">
                                <h4 class="font-medium text-green-800 mb-2">Focused Analysis</h4>
                                <p class="text-sm text-green-700">${condition.protocol.focusedAnalysis}</p>
                            </div>
                            <div class="bg-purple-50 p-4 rounded-lg">
                                <h4 class="font-medium text-purple-800 mb-2">Meta-Therapy Settings</h4>
                                <p class="text-sm text-purple-700 mb-1"><strong>Selection:</strong> ${condition.protocol.metaTherapy.selection}</p>
                                <p class="text-sm text-purple-700 mb-1"><strong>Settings:</strong> ${condition.protocol.metaTherapy.settings}</p>
                                <p class="text-sm text-purple-700 mb-1"><strong>Sessions:</strong> ${condition.protocol.metaTherapy.sessions}</p>
                                <p class="text-sm text-purple-700"><strong>Focus:</strong> ${condition.protocol.metaTherapy.focus}</p>
                            </div>
                            <div class="bg-orange-50 p-4 rounded-lg">
                                <h4 class="font-medium text-orange-800 mb-2">Vegetative Test & Imprinting</h4>
                                <p class="text-sm text-orange-700 mb-2"><strong>Testing:</strong> ${condition.protocol.vegetativeTest}</p>
                                <p class="text-sm text-orange-700"><strong>Imprinting:</strong> ${condition.protocol.imprinting}</p>
                            </div>
                        </div>
                    </div>
                    ` : ''}

                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">📝 Treatment Protocol Steps</h3>
                        <div class="space-y-3">
                            ${condition.steps.map((step, index) => `
                                <div class="flex items-start space-x-3 p-3 bg-blue-50 rounded-lg">
                                    <div class="flex-shrink-0 w-6 h-6 bg-blue-600 text-white rounded-full flex items-center justify-center text-sm font-medium">
                                        ${index + 1}
                                    </div>
                                    <p class="text-gray-700">${step}</p>
                                </div>
                            `).join('')}
                        </div>
                    </div>

                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">🎯 Target Areas</h3>
                        <div class="grid grid-cols-2 md:grid-cols-3 gap-2">
                            ${condition.targets.map(target => 
                                `<div class="px-3 py-2 bg-green-100 text-green-800 rounded text-sm text-center">${target}</div>`
                            ).join('')}
                        </div>
                    </div>

                    <div>
                        <h3 class="text-lg font-semibold text-gray-800 mb-3">⚠️ Important Notes & Medical Disclaimer</h3>
                        <ul class="space-y-2">
                            ${condition.notes.map(note => 
                                `<li class="flex items-start space-x-2">
                                    <span class="text-red-500 mt-1">•</span>
                                    <span class="text-gray-700 ${note.includes('CRITICAL') ? 'font-semibold text-red-700' : ''}">${note}</span>
                                </li>`
                            ).join('')}
                        </ul>
                    </div>
                </div>
            `;
            document.getElementById('conditionModal').classList.remove('hidden');
        }

        function closeModal() {
            document.getElementById('conditionModal').classList.add('hidden');
        }

        // Event listeners
        document.getElementById('searchInput').addEventListener('input', filterConditions);
        document.getElementById('systemFilter').addEventListener('change', filterConditions);
        document.getElementById('closeModal').addEventListener('click', closeModal);

        // Close modal when clicking outside
        document.getElementById('conditionModal').addEventListener('click', function(e) {
            if (e.target === this) {
                closeModal();
            }
        });

        // Initialize the application
        updateTotalCount();
        renderConditions();
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'972858f0973e8a59',t:'MTc1NTc2MDYxMi4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>






// =========================
// 1) Anxiety & Stress-Related Disorders
// =========================
{
    name: "Generalized Anxiety Disorder (GAD)",
    category: "mental_health",
    systems: ["Limbic system", "Prefrontal cortex", "Autonomic nervous system", "Endocrine (HPA axis)"],
    whatItIs: "Persistent and excessive anxiety/worry about multiple domains for 6+ months, difficult to control and causing distress/impairment.",
    howItAffects: "Sympathetic overactivity, HPA-axis dysregulation (cortisol), muscle tension, sleep disturbance, impaired concentration and somatic symptoms.",
    energeticMarkers: {
        flendlerScale: "Frequent brown diamonds over limbic etalons (chronic stress); intermittent red triangles with acute spikes.",
        graphNumbers: "4–5 deviations in ANS and HPA etalons indicating chronic hyperarousal.",
        anabolismCatabolism: "Red catabolism predominance in adrenal etalons; reduced blue anabolism in prefrontal regulation pathways.",
        isoline: "Chronic range 0.3–0.6 with occasional 0.7–0.8 surges during flare-ups.",
        kccValues: "KCC < 0.45 in limbic stress etalons; >0.7 in healthy relaxation etalons when improving.",
        entropyAnalysis: "E = 4–6 in ANS/HPA etalons indicating mature stress patterns.",
        biochemicalHomeostasis: "E = 1 or 7 in serotonin/GABA balance etalons suggests significant deviation.",
        vegetativeTest: "Positive response (+10–20%) to calming, GABAergic, vagal-toning preparations."
    },
    protocol: {
        initialScan: "Comprehensive CNS scan with focus on amygdala-hippocampus-prefrontal circuitry and ANS/HPA.",
        focusedAnalysis: "Drill into limbic stress etalons, adrenal regulation, vagal tone, and sleep architecture.",
        metaTherapy: {
            selection: "Select highest-stress limbic/ANS etalons (lowest KCC) plus prefrontal regulation support.",
            settings: "Level 2–3, Therapy mode, 20–30 min/area; total 30–45 min.",
            sessions: "2–3×/week for 4–6 weeks, then taper.",
            focus: "Calming hyperarousal, strengthening vagal tone, restoring cortical control."
        },
        vegetativeTest: "Test calming/adaptogen/serotonin-support frequencies; retain items with >10% improvement.",
        imprinting: "Imprint relaxation + sleep support frequencies into water or pellets; 3× daily for 2–3 weeks."
    },
    steps: [
        "Run CNS + ANS + endocrine overview scan.",
        "Target limbic stress hubs (amygdala/hippocampus) with meta-therapy.",
        "Support prefrontal regulation and vagal tone.",
        "Balance neurotransmitter signatures (GABA/serotonin).",
        "Imprint calming regimen; reassess sleep and tension."
    ],
    targets: ["Amygdala", "Hippocampus", "Prefrontal cortex", "Vagus nerve", "Adrenal glands"],
    notes: [
        "Integrate with psychotherapy and lifestyle strategies.",
        "Monitor sleep quality, caffeine intake, and breathing practices.",
        "CRITICAL: Refer for acute risk, severe impairment, or medication adjustments."
    ]
},
{
    name: "Panic Disorder",
    category: "mental_health",
    systems: ["Limbic system", "Autonomic nervous system", "Respiratory drive", "Cardiac rhythm"],
    whatItIs: "Recurrent unexpected panic attacks with persistent concern or behavioral change related to attacks.",
    howItAffects: "Sudden sympathetic spikes, hyperventilation, chest tightness, dizziness, fear of loss of control; anticipatory anxiety.",
    energeticMarkers: {
        flendlerScale: "Acute red triangles over ANS/respiratory etalons during episodes; brown diamonds with chronic sensitization.",
        graphNumbers: "5–6 spikes in ANS/cardiac rhythm etalons during panic maps.",
        anabolismCatabolism: "Catabolic dominance in adrenal/respiratory centers; transient rebound post-episode.",
        isoline: "0.6–0.9 during acute attacks; settles to 0.3–0.5 between episodes.",
        kccValues: "KCC < 0.4 in panic-coupled ANS etalons at peak.",
        entropyAnalysis: "E = 5–6 indicating unstable, high-variance autonomic patterns.",
        biochemicalHomeostasis: "Deviation in lactate/CO2 sensitivity etalons and noradrenergic tone.",
        vegetativeTest: "Strong positive to CO2 tolerance/breath regulation and vagal support frequencies."
    },
    protocol: {
        initialScan: "Brain-ANS overview with cardio-respiratory focus.",
        focusedAnalysis: "Amygdala, hypothalamus, brainstem respiratory centers, cardiac rhythm.",
        metaTherapy: {
            selection: "Anti-panic resonance programs + vagal stabilization + respiratory rhythm training.",
            settings: "Level 2, 15–25 min; gradual exposure style over multiple sessions.",
            sessions: "2×/week for 4–8 weeks.",
            focus: "Reduce spiking, enhance CO2 tolerance and interoceptive safety."
        },
        vegetativeTest: "Test breath regulation, grounding, and anti-palpitations sets; keep >12% benefit.",
        imprinting: "Imprint ‘calm breath’ and ‘cardio-steady’ frequencies; use before triggers."
    },
    steps: [
        "Map panic trigger signature and ANS spikes.",
        "Stabilize respiratory rhythm and CO2 tolerance.",
        "Apply anti-panic/vagal meta-therapy.",
        "Cardiac steadiness support; rehearse calm response.",
        "Imprint pre-emptive calming protocol for daily use."
    ],
    targets: ["Amygdala", "Hypothalamus", "Brainstem respiratory centers", "Vagus nerve", "Cardiac conduction"],
    notes: [
        "Rule out cardiac/thyroid/asthma mimics.",
        "Combine with CBT (interoceptive exposure) for durable gains.",
        "Emergency plan for severe acute episodes."
    ]
},
{
    name: "Social Anxiety Disorder",
    category: "mental_health",
    systems: ["Limbic system", "Prefrontal cortex", "Autonomic nervous system"],
    whatItIs: "Marked fear or anxiety in social situations with fear of scrutiny, negative evaluation, or embarrassment.",
    howItAffects: "Performance fear, blushing/tremor, avoidance, anticipatory worry; impaired social/occupational function.",
    energeticMarkers: {
        flendlerScale: "Brown diamonds in social-threat limbic etalons; mild red triangles with performance triggers.",
        graphNumbers: "4–5 deviations in social-threat circuits (amygdala-prefrontal).",
        anabolismCatabolism: "Reduced anabolism in prefrontal regulation; catabolic bias under anticipation.",
        isoline: "0.4–0.7 near social events; 0.3–0.5 baseline.",
        kccValues: "KCC < 0.5 in evaluative-threat etalons pre-exposure.",
        entropyAnalysis: "E = 4–5 with predictable trigger-linked variability.",
        biochemicalHomeostasis: "Serotonergic modulation etalons often deviant; beta-adrenergic overactivity.",
        vegetativeTest: "Positive response to calm-focus, vagal, and beta-quieting frequencies."
    },
    protocol: {
        initialScan: "CNS scan emphasizing social threat circuitry.",
        focusedAnalysis: "Amygdala reactivity vs. prefrontal top-down control.",
        metaTherapy: {
            selection: "Calm-focus + confidence/voice resonance + vagal toning.",
            settings: "Level 2–3, 20–30 min.",
            sessions: "2×/week for 6 weeks during exposure work.",
            focus: "Reduce anticipatory arousal; enhance executive regulation."
        },
        vegetativeTest: "Test calm-exposure aids; keep those with >10% improvement.",
        imprinting: "Imprint ‘social ease’ set for pre-event dosing."
    },
    steps: [
        "Identify evaluative-threat signature.",
        "Downshift limbic reactivity; uptrain prefrontal control.",
        "Pair meta-therapy with graded exposure schedule.",
        "Train breathing/grounding before events.",
        "Reassess confidence, avoidance, and recovery time."
    ],
    targets: ["Amygdala", "Prefrontal cortex", "Vagus nerve", "Adrenal glands"],
    notes: [
        "Coordinate with CBT for exposure and cognitive restructuring.",
        "Track specific goals (presentations, meetings, calls).",
        "Consider speech/voice coaching add-ons for performance cases."
    ]
},
{
    name: "Phobias (Specific Phobia / Agoraphobia)",
    category: "mental_health",
    systems: ["Limbic system", "Autonomic nervous system"],
    whatItIs: "Intense fear of a specific object/situation (specific phobia) or fear of situations where escape/help may be difficult (agoraphobia).",
    howItAffects: "Rapid fear response, avoidance, panic-like symptoms when exposed; functional limitations.",
    energeticMarkers: {
        flendlerScale: "Red triangles on trigger exposure; brown diamonds with chronic avoidance patterns.",
        graphNumbers: "5–6 spikes in limbic threat etalons upon cueing.",
        anabolismCatabolism: "Transient catabolic surges with trigger imagery; recovery with safety cues.",
        isoline: "0.7–0.9 during exposure; 0.3–0.5 neutral.",
        kccValues: "Lowest KCC in trigger-linked etalons; improves with graduated exposure.",
        entropyAnalysis: "E = 5–6 indicating high volatility around triggers.",
        biochemicalHomeostasis: "Noradrenergic surge markers deviate; GABAergic tone reduced transiently.",
        vegetativeTest: "Strong positive to graded-exposure support and safety-anchor frequencies."
    },
    protocol: {
        initialScan: "CNS+ANS overview; capture trigger-linked pattern using guided imagery if tolerated.",
        focusedAnalysis: "Amygdala-trigger pathway mapping; safety cue anchoring.",
        metaTherapy: {
            selection: "Phobia-desensitization resonance + vagal safety + calm exposure support.",
            settings: "Level 2, 15–25 min; short, repeated sessions around exposures.",
            sessions: "2×/week for 4–6 weeks.",
            focus: "Reduce reactivity; anchor calm response to graded triggers."
        },
        vegetativeTest: "Test safety-anchor and calm-exposure frequencies (>12% gain).",
        imprinting: "Imprint ‘trigger calm’ set; use before/after exposures."
    },
    steps: [
        "Establish safe baseline; brief imagery of trigger if appropriate.",
        "Apply desensitization + vagal safety meta-therapy.",
        "Run short sessions around graded exposure steps.",
        "Reinforce with safety-anchor imprinting.",
        "Track approach behavior and symptom drop."
    ],
    targets: ["Amygdala", "Hippocampus (context)", "Vagus nerve"],
    notes: [
        "Use gentle pacing; avoid flooding.",
        "Integrate with exposure-based CBT for best outcomes.",
        "Medical rule-out for agoraphobia-like dizziness/cardiac symptoms when indicated."
    ]
},
{
    name: "Post-Traumatic Stress Disorder (PTSD)",
    category: "mental_health",
    systems: ["Limbic system", "Hippocampus", "Prefrontal cortex", "Endocrine (HPA axis)", "Sleep circuits"],
    whatItIs: "Persistent re-experiencing, avoidance, negative mood/cognition changes, and hyperarousal following trauma (duration >1 month).",
    howItAffects: "Amygdala hyperreactivity, hippocampal contextual memory disruption, HPA dysregulation, sleep disturbance (nightmares).",
    energeticMarkers: {
        flendlerScale: "Chronic brown diamonds across limbic/HPA; red triangles with trauma cues.",
        graphNumbers: "4–6 deviations in memory reconsolidation and arousal circuits.",
        anabolismCatabolism: "Catabolic dominance with impaired restorative anabolism in sleep etalons.",
        isoline: "0.5–0.9 depending on cueing; unstable baselines.",
        kccValues: "KCC < 0.45 in trauma imprint etalons.",
        entropyAnalysis: "E = 5–6 (unstable) across arousal and memory tracks.",
        biochemicalHomeostasis: "Cortisol rhythm deviation; noradrenergic overdrive markers.",
        vegetativeTest: "Positive to trauma-release, grounding, and sleep-normalization sets."
    },
    protocol: {
        initialScan: "CNS with memory/arousal focus; endocrine (adrenal) and sleep system review.",
        focusedAnalysis: "Amygdala-hippocampus-prefrontal circuits; REM regulation.",
        metaTherapy: {
            selection: "Trauma-release and safety programs + sleep normalization.",
            settings: "Level 2, 20–30 min; proceed gently to avoid re-traumatization.",
            sessions: "Weekly/biweekly long-term adjunct.",
            focus: "Reduce hyperarousal, restore contextual safety and sleep architecture."
        },
        vegetativeTest: "Prioritize items that improve calm and sleep metrics (>10%).",
        imprinting: "Night-use imprint for sleep stabilization and nightmare reduction."
    },
    steps: [
        "Map trauma imprint and arousal patterns.",
        "Stabilize HPA axis and vagal tone.",
        "Support memory reconsolidation safety.",
        "Normalize sleep stages and dream stress.",
        "Review triggers and resilience markers."
    ],
    targets: ["Amygdala", "Hippocampus", "Prefrontal cortex", "Adrenal glands", "Sleep/REM centers"],
    notes: [
        "CRITICAL: Coordinate with trauma-informed psychotherapy.",
        "Avoid provocative cueing without support.",
        "Safety planning for dissociation or acute distress."
    ]
},
{
    name: "Acute Stress Disorder",
    category: "mental_health",
    systems: ["Limbic system", "HPA axis", "Autonomic nervous system"],
    whatItIs: "Trauma-related symptoms (intrusion, negative mood, dissociation, avoidance, arousal) occurring within 3 days to 1 month after event.",
    howItAffects: "Acute hyperarousal, sleep disturbance, dissociation, startle; may progress to PTSD if unresolved.",
    energeticMarkers: {
        flendlerScale: "Prominent red triangles early post-event; brown diamonds appear with persistent stress.",
        graphNumbers: "5–6 spikes in arousal circuits; variable prefrontal control.",
        anabolismCatabolism: "Strong catabolic surge; limited anabolism in recovery windows.",
        isoline: "0.7–0.9 acutely; declines toward 0.4–0.6 with stabilization.",
        kccValues: "Very low KCC in acute arousal etalons (<0.4).",
        entropyAnalysis: "E = 6 (high volatility) immediately post-trauma.",
        biochemicalHomeostasis: "Cortisol/adrenaline markers deviated; sleep/REM disruption.",
        vegetativeTest: "Positive to grounding, safety, and sleep support frequencies."
    },
    protocol: {
        initialScan: "CNS/ANS/endocrine snapshot with emphasis on arousal and sleep.",
        focusedAnalysis: "Amygdala, startle pathways, adrenal outputs, REM regulation.",
        metaTherapy: {
            selection: "Crisis-calming + safety containment + sleep normalization.",
            settings: "Level 1–2 early; short gentle sessions 15–20 min.",
            sessions: "2–3×/week for 2–3 weeks.",
            focus: "Immediate downshift of arousal and restoration of sleep."
        },
        vegetativeTest: "Keep items that rapidly improve calm or sleep latency.",
        imprinting: "Short-term ‘acute calm’ imprint; nightly sleep support."
    },
    steps: [
        "Establish safety and grounding baseline.",
        "Apply crisis-calming protocols.",
        "Normalize sleep cycles.",
        "Support vagal tone and recovery windows.",
        "Reassess weekly for resolution vs. referral."
    ],
    targets: ["Amygdala", "Startle circuits", "Vagus nerve", "Adrenal glands", "Sleep centers"],
    notes: [
        "Stabilization first; avoid deep trauma processing acutely.",
        "Coordinate with medical/psychological care.",
        "Escalate if dissociation, suicidality, or severe impairment emerges."
    ]
},
{
    name: "Adjustment Disorder with Anxiety",
    category: "mental_health",
    systems: ["Limbic system", "Prefrontal cortex", "Autonomic nervous system"],
    whatItIs: "Emotional/behavioral symptoms in response to identifiable stressor(s), onset within 3 months, causing distress/impairment; does not meet criteria for another disorder.",
    howItAffects: "Situational anxiety, worry, tension, sleep difficulty; typically resolves as stressor adapts or resolves.",
    energeticMarkers: {
        flendlerScale: "Brown diamonds in limbic etalons with situational peaks.",
        graphNumbers: "4–5 deviations tied to stressor context.",
        anabolismCatabolism: "Temporary catabolic bias; normalizes with coping.",
        isoline: "0.4–0.7 depending on stressor intensity.",
        kccValues: "Moderately low KCC in stressor-linked etalons; improves with adaptation.",
        entropyAnalysis: "E = 3–4 (moderate) with predictable context link.",
        biochemicalHomeostasis: "Mild serotonergic/GABA deviations.",
        vegetativeTest: "Positive to coping/grounding and sleep-support sets."
    },
    protocol: {
        initialScan: "CNS/ANS scan emphasizing context-linked etalons.",
        focusedAnalysis: "Map stressor associations; prefrontal regulation support.",
        metaTherapy: {
            selection: "Calm-adaptation + resilience + sleep support.",
            settings: "Level 2–3, 20–30 min.",
            sessions: "Weekly for 4–6 weeks.",
            focus: "Facilitate adaptation and reduce tension."
        },
        vegetativeTest: "Choose items that enhance coping (>8–10%).",
        imprinting: "Daily ‘resilience & calm’ imprint for 2–3 weeks."
    },
    steps: [
        "Identify stressor-linked energetic patterns.",
        "Apply calm-adaptation meta-therapy.",
        "Reinforce sleep and daily recovery practices.",
        "Introduce resilience imprinting.",
        "Reassess as stressor changes or resolves."
    ],
    targets: ["Amygdala", "Prefrontal cortex", "Vagus nerve"],
    notes: [
        "Short-term, goal-focused support.",
        "Encourage problem-solving and boundary setting.",
        "Refer if symptoms persist >6 months or escalate."
    ]
},
{
    name: "Reactive/Acute Stress Response",
    category: "mental_health",
    systems: ["Autonomic nervous system", "Limbic system", "Endocrine (HPA axis)"],
    whatItIs: "Immediate physiological and emotional response to acute stressors; typically transient once stressor ends.",
    howItAffects: "Short-lived hyperarousal, tachycardia, muscle tension, irritability; may impair performance temporarily.",
    energeticMarkers: {
        flendlerScale: "Transient red triangles in ANS; resolve quickly post-stressor.",
        graphNumbers: "5–6 spikes during stress; rapid return toward baseline.",
        anabolismCatabolism: "Brief catabolic surge; recovery anabolism with rest.",
        isoline: "0.7–0.9 during stress; 0.3–0.5 after resolution.",
        kccValues: "Low KCC in arousal etalons acutely; normalize with recovery.",
        entropyAnalysis: "E = 5 acute; falls to 2–3 on recovery.",
        biochemicalHomeostasis: "Adrenaline/cortisol peaks; normalize after rest.",
        vegetativeTest: "Strong response to rapid-calming and breathing sets."
    },
    protocol: {
        initialScan: "Quick ANS/HPA snapshot during/after stress if possible.",
        focusedAnalysis: "Arousal centers and vagal tone.",
        metaTherapy: {
            selection: "Rapid-calming + breath/vagal entrainment.",
            settings: "Level 1–2, 10–20 min.",
            sessions: "As-needed around stress events.",
            focus: "Fast downshift and recovery."
        },
        vegetativeTest: "Choose fast-acting calm/breath programs.",
        imprinting: "Carry ‘rapid reset’ imprint for on-demand use."
    },
    steps: [
        "Assess arousal state and triggers.",
        "Run rapid-calming meta-therapy.",
        "Train breathing cadence and vagal entrainment.",
        "Imprint quick reset protocol.",
        "Review recovery markers (HRV, sleep)."
    ],
    targets: ["Vagus nerve", "Adrenal glands", "Amygdala"],
    notes: [
        "Educate on micro-recovery (breaks, hydration, posture).",
        "Useful before performances or high-stress tasks.",
        "Seek medical review if symptoms persist or escalate."
    ]
}
// =========================
// 1) Anxiety & Stress-Related Disorders
// =========================
{
    name: "Generalized Anxiety Disorder (GAD)",
    category: "mental_health",
    systems: ["Limbic system", "Autonomic nervous system", "Neurotransmitter regulation"],
    whatItIs: "Chronic and excessive worry about multiple areas of life, often disproportionate to actual circumstances.",
    howItAffects: "Hyperactive sympathetic nervous system, increased cortisol, restlessness, muscle tension, sleep disturbance.",
    energeticMarkers: {
        flendlerScale: "Elevated stress markers",
        vegetativeTest: "Sympathetic dominance",
        entropyAnalysis: "Fluctuating ANS regulation"
    },
    protocol: {
        initialScan: "Full brain and autonomic nervous system scan",
        focusedAnalysis: "Limbic system and prefrontal cortex",
        metaTherapy: {
            selection: "Calming, serotonin-dopamine balancing",
            settings: "Low-intensity, longer sessions",
            sessions: "3-5 per week, 30–40 min",
            focus: "Reduce hyperarousal, stabilize ANS"
        },
        imprinting: "Calm and relaxation frequencies onto water or carrier"
    },
    steps: [
        "Scan limbic structures (amygdala, hippocampus)",
        "Balance autonomic nervous system",
        "Support neurotransmitter homeostasis",
        "Run meta-therapy with stress relief programs",
        "Reinforce with imprinting of calming frequencies"
    ],
    targets: ["Amygdala", "Prefrontal cortex", "Adrenal glands"],
    notes: [
        "CRITICAL: Severe anxiety should also be managed with psychotherapy/medical support",
        "Complementary techniques: breathing, meditation, grounding"
    ]
},
{
    name: "Panic Disorder",
    category: "mental_health",
    systems: ["Limbic system", "Autonomic nervous system"],
    whatItIs: "Recurrent unexpected panic attacks with fear of future episodes.",
    howItAffects: "Sudden sympathetic overdrive, palpitations, hyperventilation, fear of death.",
    energeticMarkers: {
        flendlerScale: "Sudden ANS spikes",
        vegetativeTest: "Erratic parasympathetic rebound"
    },
    protocol: {
        initialScan: "Brain regions + ANS",
        focusedAnalysis: "Amygdala, hypothalamus",
        metaTherapy: {
            selection: "Anti-panic resonance",
            settings: "Gentle, progressive exposure",
            sessions: "2-3 per week",
            focus: "Stabilization and prevention"
        },
        imprinting: "Resonance frequencies for calm stabilization"
    },
    steps: [
        "Identify panic-related neuro-signatures",
        "Normalize autonomic regulation",
        "Apply calming frequency therapy",
        "Stabilize heart and respiratory rhythms"
    ],
    targets: ["Amygdala", "Hypothalamus", "Vagus nerve"],
    notes: [
        "Ensure medical evaluation for cardiac mimics",
        "Use as support alongside CBT or medication"
    ]
},
{
    name: "Post-Traumatic Stress Disorder (PTSD)",
    category: "mental_health",
    systems: ["Limbic system", "Amygdala", "HPA axis"],
    whatItIs: "Persistent psychological distress following traumatic events, with flashbacks, hypervigilance, and avoidance.",
    howItAffects: "Overactive amygdala, dysregulated cortisol response, sleep disturbance.",
    energeticMarkers: {
        entropyAnalysis: "Chronic dysregulation patterns",
        biochemicalHomeostasis: "Elevated cortisol",
        vegetativeTest: "ANS hyperactivity"
    },
    protocol: {
        initialScan: "Full CNS + endocrine system scan",
        focusedAnalysis: "Amygdala, hippocampus, adrenal glands",
        metaTherapy: {
            selection: "Trauma release and calming",
            settings: "Low frequency, progressive work",
            sessions: "Long-term, weekly or biweekly",
            focus: "Reduce hyperarousal, stabilize HPA axis"
        },
        imprinting: "Trauma release support remedies"
    },
    steps: [
        "Map trauma imprint patterns",
        "Support nervous system recovery",
        "Stabilize adrenal and cortisol response",
        "Apply trauma-release frequency protocols"
    ],
    targets: ["Amygdala", "Hippocampus", "Adrenal glands"],
    notes: [
        "CRITICAL: Must be under psychiatric/therapeutic care",
        "Energetic work should be gentle, non-triggering"
    ]
},
// =========================
// AUTOIMMUNE CONDITIONS
// =========================
{
    name: "Lupus (SLE)",
    category: "autoimmune",
    systems: ["Immune System", "Multisystem"],
    whatItIs: "Systemic Lupus Erythematosus is an autoimmune condition where the immune system attacks healthy tissues and organs.",
    howItAffects: "Can cause joint pain, skin rashes, fatigue, kidney involvement, heart inflammation, and neurological symptoms.",
    steps: [
        "Comprehensive immune system scan",
        "Identify systemic inflammatory etalons",
        "Immune modulation frequency therapy",
        "Meta-therapy with organ protection focus",
        "Long-term monitoring of affected systems"
    ],
    targets: ["Immune cells", "Kidneys", "Skin", "Heart", "Nervous system"],
    notes: [
        "CRITICAL: Rheumatology follow-up required",
        "Avoid sun exposure due to photosensitivity",
        "Monitor kidney function regularly"
    ]
},
{
    name: "Hashimoto’s Thyroiditis",
    category: "autoimmune",
    systems: ["Endocrine System"],
    whatItIs: "An autoimmune thyroid condition where the immune system attacks the thyroid gland, often causing hypothyroidism.",
    howItAffects: "Leads to fatigue, weight gain, cold intolerance, hair loss, and depression.",
    steps: [
        "Thyroid gland scan",
        "Analysis of autoantibody activity",
        "Immune calming frequency therapy",
        "Meta-therapy with thyroid support",
        "Follow-up on thyroid hormone balance"
    ],
    targets: ["Thyroid gland", "TSH receptors", "Immune system"],
    notes: [
        "Monitor TSH and antibody levels",
        "Medication often required (levothyroxine)",
        "Coordinate with endocrinologist"
    ]
},

// =========================
// INFECTIOUS CONDITIONS
// =========================
{
    name: "Influenza",
    category: "infectious",
    systems: ["Respiratory System", "Immune System"],
    whatItIs: "A viral respiratory infection caused by influenza viruses.",
    howItAffects: "Causes fever, cough, body aches, fatigue, and can lead to complications like pneumonia.",
    steps: [
        "Respiratory and immune system scan",
        "Detection of viral burden",
        "Anti-viral frequency therapy",
        "Immune support meta-therapy",
        "Reassessment after symptom resolution"
    ],
    targets: ["Respiratory epithelium", "Immune cells", "Lung tissue"],
    notes: [
        "Hydration and rest critical",
        "Antiviral drugs may be required",
        "Monitor for complications in elderly or children"
    ]
},
{
    name: "Tuberculosis (TB)",
    category: "infectious",
    systems: ["Respiratory System", "Immune System"],
    whatItIs: "A bacterial infection caused by Mycobacterium tuberculosis, mainly affecting the lungs.",
    howItAffects: "Symptoms include chronic cough, night sweats, fever, and weight loss. Can spread to bones and brain.",
    steps: [
        "Lung scan focusing on granuloma patterns",
        "Identify bacterial burden",
        "Immune strengthening frequency therapy",
        "Meta-therapy with lung repair support",
        "Monitor infectious clearance"
    ],
    targets: ["Lungs", "Lymph nodes", "Immune cells"],
    notes: [
        "CRITICAL: Requires full antibiotic regimen",
        "Strict medical supervision required",
        "Highly contagious"
    ]
},

// =========================
// ONCOLOGY
// =========================
{
    name: "Breast Cancer",
    category: "oncology",
    systems: ["Oncology", "Endocrine", "Immune System"],
    whatItIs: "A malignant tumor that develops from breast tissue.",
    howItAffects: "Can spread locally or metastasize to bone, lungs, or liver.",
    steps: [
        "Breast tissue scan for abnormal etalons",
        "Identify malignant energetic markers",
        "Immune modulation frequency therapy",
        "Meta-therapy with cellular repair support",
        "Supportive imprinting for recovery"
    ],
    targets: ["Breast tissue", "Immune system", "Lymph nodes"],
    notes: [
        "CRITICAL: Oncology treatment (surgery, chemo, radiation) must not be delayed",
        "Energetic therapy is complementary only",
        "Regular imaging follow-up required"
    ]
},
{
    name: "Prostate Cancer",
    category: "oncology",
    systems: ["Oncology", "Urology", "Endocrine"],
    whatItIs: "A malignant growth in the prostate gland, common in older men.",
    howItAffects: "Can cause urinary problems, bone pain (if metastasized), and sexual dysfunction.",
    steps: [
        "Prostate gland scan",
        "Identify cancer-related energetic etalons",
        "Immune support frequency therapy",
        "Meta-therapy with prostate protection",
        "Monitor energetic changes during medical treatment"
    ],
    targets: ["Prostate", "Immune system", "Urinary tract"],
    notes: [
        "Medical management essential",
        "Monitor PSA levels",
        "Complementary role only"
    ]
},

// =========================
// PEDIATRIC CONDITIONS
// =========================
{
    name: "ADHD (Attention Deficit Hyperactivity Disorder)",
    category: "pediatric",
    systems: ["Neurology & CNS", "Psychiatry"],
    whatItIs: "A neurodevelopmental disorder characterized by inattention, hyperactivity, and impulsivity.",
    howItAffects: "Affects school performance, social behavior, and emotional regulation.",
    steps: [
        "Neuro-psychiatric scan",
        "Focus on attention and impulse-control etalons",
        "Brain balancing frequency therapy",
        "Meta-therapy with concentration support",
        "Regular re-evaluation of progress"
    ],
    targets: ["Prefrontal cortex", "Dopamine pathways", "Nervous system"],
    notes: [
        "Behavioral therapy important",
        "Coordinate with pediatric neurologist",
        "Medication may be prescribed"
    ]
},
{
    name: "Autism Spectrum Disorder",
    category: "pediatric",
    systems: ["Neurology & CNS", "Psychiatry"],
    whatItIs: "A developmental disorder affecting communication, behavior, and social interaction.",
    howItAffects: "Children may show repetitive behaviors, sensory sensitivities, and challenges with speech or interaction.",
    steps: [
        "Brain development scan",
        "Analysis of communication and sensory pathways",
        "Frequency therapy for sensory integration",
        "Meta-therapy with emotional balance",
        "Ongoing support and follow-up"
    ],
    targets: ["Nervous system", "Sensory pathways", "Social-emotional circuits"],
    notes: [
        "Requires multidisciplinary support",
        "Therapies (speech, OT, behavioral) are primary",
        "Energetic therapy is complementary"
    ]
},

// =========================
// OPHTHALMOLOGY
// =========================
{
    name: "Glaucoma",
    category: "ophthalmology",
    systems: ["Ophthalmology", "Neurology"],
    whatItIs: "A condition where increased intraocular pressure damages the optic nerve.",
    howItAffects: "Leads to progressive, irreversible vision loss if untreated.",
    steps: [
        "Eye scan focusing on optic nerve and pressure etalons",
        "Frequency therapy for optic nerve support",
        "Meta-therapy with ocular circulation support",
        "Monitoring of visual field stability"
    ],
    targets: ["Optic nerve", "Retina", "Aqueous humor drainage"],
    notes: [
        "CRITICAL: Ophthalmologist treatment required",
        "Monitor intraocular pressure regularly",
        "Vision loss is irreversible"
    ]
},
{
    name: "Macular Degeneration",
    category: "ophthalmology",
    systems: ["Ophthalmology"],
    whatItIs: "A retinal disease that damages the macula, impairing central vision.",
    howItAffects: "Causes difficulty reading, recognizing faces, and seeing fine details.",
    steps: [
        "Retinal and macular scan",
        "Analysis of vascular supply",
        "Frequency therapy for retinal support",
        "Meta-therapy with antioxidant imprinting",
        "Reassessment every 3–6 months"
    ],
    targets: ["Macula", "Retinal blood vessels"],
    notes: [
        "Nutritional support is important (lutein, antioxidants)",
        "Monitor with ophthalmology exams",
        "Irreversible once advanced"
    ]
},

// =========================
// ENT (Ear, Nose, Throat)
// =========================
{
    name: "Chronic Sinusitis",
    category: "ent",
    systems: ["ENT", "Respiratory"],
    whatItIs: "Inflammation of the sinuses lasting more than 12 weeks.",
    howItAffects: "Leads to nasal blockage, headaches, facial pain, and post-nasal drip.",
    steps: [
        "Sinus scan focusing on mucosal inflammation",
        "Frequency therapy for sinus drainage",
        "Meta-therapy with anti-inflammatory support",
        "Monitor for infection recurrence"
    ],
    targets: ["Sinuses", "Nasal mucosa", "Immune cells"],
    notes: [
        "Saline rinses are supportive",
        "Monitor for bacterial superinfection",
        "Allergy management may help"
    ]
},
{
    name: "Otitis Media (Middle Ear Infection)",
    category: "ent",
    systems: ["ENT"],
    whatItIs: "Infection or inflammation of the middle ear, common in children.",
    howItAffects: "Causes ear pain, fever, fluid buildup, and possible hearing loss.",
    steps: [
        "Ear scan with focus on tympanic membrane",
        "Detection of fluid and infection markers",
        "Frequency therapy for inflammation",
        "Meta-therapy with immune support",
        "Reevaluation after recovery"
    ],
    targets: ["Middle ear", "Eustachian tube", "Immune cells"],
    notes: [
        "Pediatric follow-up required",
        "Monitor for chronic ear infections",
        "May require antibiotics or surgery"
    ]
}
// =========================
// PART 1: Anxiety & Stress-Related Disorders
// =========================

{
    name: "Generalized Anxiety Disorder (GAD)",
    category: "mental_health",
    systems: ["Limbic system", "Autonomic nervous system", "Neurotransmitter regulation"],
    whatItIs: "Chronic and excessive worry about multiple aspects of daily life, often disproportionate to actual circumstances.",
    howItAffects: "Leads to sympathetic overactivation, cortisol dysregulation, muscle tension, digestive upset, and persistent restlessness.",
    energeticMarkers: {
        flendlerScale: "Elevated stress markers",
        vegetativeTest: "Sympathetic dominance",
        entropyAnalysis: "Fluctuating ANS regulation"
    },
    protocol: {
        initialScan: "Full brain and autonomic nervous system scan",
        focusedAnalysis: "Limbic system, prefrontal cortex, adrenal function",
        metaTherapy: {
            selection: "Calming, serotonin-dopamine balancing",
            settings: "Low-intensity, 25–35 Hz",
            sessions: "3–5 per week, 30–40 minutes",
            focus: "Reduce hyperarousal and stabilize ANS"
        },
        imprinting: "Imprint calming frequencies onto water for daily intake"
    },
    steps: [
        "Scan limbic system, amygdala, hippocampus",
        "Stabilize autonomic nervous system patterns",
        "Balance neurotransmitter-related frequency bands",
        "Run anti-stress meta-therapy protocols",
        "Support with imprinting for self-regulation"
    ],
    targets: ["Amygdala", "Prefrontal cortex", "Adrenal glands", "Vagus nerve"],
    notes: [
        "CRITICAL: Should be managed in combination with psychotherapy and/or medication when needed.",
        "Energetic protocols support but do not replace medical treatment."
    ]
},
{
    name: "Panic Disorder",
    category: "mental_health",
    systems: ["Limbic system", "Autonomic nervous system"],
    whatItIs: "Recurrent, unexpected panic attacks characterized by intense fear and physical symptoms such as palpitations, shortness of breath, and dizziness.",
    howItAffects: "Sudden sympathetic activation, respiratory alkalosis, heart rhythm irregularities, and persistent fear of recurrence.",
    energeticMarkers: {
        flendlerScale: "Sudden ANS spikes",
        vegetativeTest: "Erratic parasympathetic rebound",
        entropyAnalysis: "Abrupt dysregulation"
    },
    protocol: {
        initialScan: "Brain and autonomic nervous system scan",
        focusedAnalysis: "Amygdala, hypothalamus, cardiac rhythm",
        metaTherapy: {
            selection: "Anti-panic calming resonance",
            settings: "Progressive desensitization, 20–30 Hz",
            sessions: "2–3 per week",
            focus: "Stabilization and prevention of attacks"
        },
        imprinting: "Resonance frequencies for calm stabilization"
    },
    steps: [
        "Identify panic-related neuro-signatures",
        "Normalize autonomic nervous system regulation",
        "Balance cardiovascular rhythm",
        "Apply calming resonance frequencies"
    ],
    targets: ["Amygdala", "Hypothalamus", "Cardiac regulation centers"],
    notes: [
        "Ensure medical evaluation to rule out cardiac/respiratory mimics.",
        "Supportive alongside CBT and pharmacological care."
    ]
},
{
    name: "Social Anxiety Disorder",
    category: "mental_health",
    systems: ["Limbic system", "Prefrontal cortex"],
    whatItIs: "Persistent fear of social or performance situations due to concern of embarrassment or scrutiny.",
    howItAffects: "Heightened amygdala reactivity, reduced prefrontal inhibitory control, dysregulated serotonin activity.",
    energeticMarkers: {
        vegetativeTest: "Mild sympathetic dominance",
        entropyAnalysis: "Fear-based resonance patterns"
    },
    protocol: {
        initialScan: "Brain regions associated with fear processing",
        focusedAnalysis: "Amygdala-prefrontal circuits",
        metaTherapy: {
            selection: "Confidence and calm-inducing frequencies",
            settings: "Low frequency resonance, 20–25 Hz",
            sessions: "2–3 per week",
            focus: "Reduce limbic overreactivity"
        },
        imprinting: "Confidence and self-esteem support remedies"
    },
    steps: [
        "Target amygdala overactivation",
        "Reinforce prefrontal inhibitory pathways",
        "Reduce anticipatory anxiety resonance patterns"
    ],
    targets: ["Amygdala", "Prefrontal cortex", "Serotonin pathways"],
    notes: [
        "Exposure therapy and coaching may enhance energetic outcomes.",
        "Integrate lifestyle and breathing exercises."
    ]
},
{
    name: "Phobias (Specific & Agoraphobia)",
    category: "mental_health",
    systems: ["Limbic system", "Amygdala"],
    whatItIs: "Intense, irrational fear triggered by specific objects, situations, or environments.",
    howItAffects: "Conditioned fear responses, exaggerated startle reflex, avoidance behaviors.",
    energeticMarkers: {
        entropyAnalysis: "Fear imprint signatures",
        vegetativeTest: "ANS hyperreactivity during triggers"
    },
    protocol: {
        initialScan: "Fear circuits within brain",
        focusedAnalysis: "Amygdala, hypothalamus",
        metaTherapy: {
            selection: "Desensitization and calming",
            settings: "Gradual exposure frequency programs",
            sessions: "Weekly",
            focus: "Reconditioning maladaptive fear responses"
        },
        imprinting: "Desensitization frequencies for gradual exposure"
    },
    steps: [
        "Identify resonance of phobic triggers",
        "Apply progressive desensitization",
        "Recondition autonomic response patterns"
    ],
    targets: ["Amygdala", "Hypothalamus", "Limbic circuits"],
    notes: [
        "Gradual approach is critical – avoid overload.",
        "Best combined with behavioral therapy."
    ]
},
{
    name: "Post-Traumatic Stress Disorder (PTSD)",
    category: "mental_health",
    systems: ["Limbic system", "Amygdala", "HPA axis"],
    whatItIs: "Persistent psychological distress following traumatic events, with flashbacks, hypervigilance, and avoidance.",
    howItAffects: "Hyperactive amygdala, impaired hippocampal regulation, disrupted cortisol rhythms, fragmented sleep.",
    energeticMarkers: {
        entropyAnalysis: "Chronic dysregulation patterns",
        biochemicalHomeostasis: "Elevated cortisol",
        vegetativeTest: "ANS hyperactivity"
    },
    protocol: {
        initialScan: "Full CNS and endocrine system scan",
        focusedAnalysis: "Amygdala, hippocampus, adrenal glands",
        metaTherapy: {
            selection: "Trauma release and nervous system calming",
            settings: "Gentle, low-frequency resonance",
            sessions: "Weekly or biweekly, long-term",
            focus: "Reduce hyperarousal and stabilize HPA axis"
        },
        imprinting: "Trauma-release supportive remedies"
    },
    steps: [
        "Map trauma imprint patterns",
        "Support hippocampal-amygdala balance",
        "Stabilize adrenal function and cortisol response",
        "Apply gentle trauma-release protocols"
    ],
    targets: ["Amygdala", "Hippocampus", "Adrenal glands"],
    notes: [
        "MUST be combined with trauma-informed therapy.",
        "Avoid over-intensity to prevent retraumatization."
    ]
},
{
    name: "Acute Stress Disorder",
    category: "mental_health",
    systems: ["Limbic system", "ANS"],
    whatItIs: "Short-term stress reaction following trauma, lasting days to weeks.",
    howItAffects: "Heightened fear responses, autonomic imbalance, disturbed sleep, intrusive memories.",
    energeticMarkers: {
        entropyAnalysis: "Temporary stress signature",
        vegetativeTest: "Increased sympathetic response"
    },
    protocol: {
        initialScan: "Full nervous system scan",
        focusedAnalysis: "Amygdala, hippocampus",
        metaTherapy: {
            selection: "Stress relief and nervous system stabilization",
            settings: "Low-intensity calming frequencies",
            sessions: "Daily or every other day",
            focus: "Reduce stress load and support recovery"
        },
        imprinting: "Calming support remedies"
    },
    steps: [
        "Stabilize autonomic nervous system",
        "Reduce acute stress imprints",
        "Support sleep regulation"
    ],
    targets: ["Amygdala", "Hypothalamus", "Hippocampus"],
    notes: [
        "Often self-resolving, but monitor for PTSD progression.",
        "Energetic support may prevent chronicization."
    ]
},
{
    name: "Adjustment Disorder with Anxiety",
    category: "mental_health",
    systems: ["Limbic system", "Neurotransmitter pathways"],
    whatItIs: "Emotional or behavioral symptoms in response to a stressful life event, exceeding normal adjustment reactions.",
    howItAffects: "Heightened anxiety, restlessness, impaired coping, possible somatic symptoms.",
    energeticMarkers: {
        vegetativeTest: "Mild ANS imbalance",
        entropyAnalysis: "Situational stress signatures"
    },
    protocol: {
        initialScan: "Emotional processing circuits",
        focusedAnalysis: "Limbic system and ANS",
        metaTherapy: {
            selection: "Adaptation and resilience frequencies",
            settings: "Short supportive sessions",
            sessions: "2–3 per week",
            focus: "Stabilization and resilience strengthening"
        },
        imprinting: "Resilience imprint onto water"
    },
    steps: [
        "Identify stressor-linked imprints",
        "Support nervous system adaptation",
        "Promote resilience through frequency reinforcement"
    ],
    targets: ["Amygdala", "Hippocampus", "Adrenal support"],
    notes: [
        "Typically temporary – support adaptation.",
        "Consider counseling alongside energetic therapy."
    ]
}
