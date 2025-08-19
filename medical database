<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bioplasm NLS V6 - Complete Protocol Database</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap');
        
        body {
            font-family: 'Inter', sans-serif;
        }
        
        .gradient-bg {
            background: linear-gradient(135deg, #1e3a8a 0%, #3730a3 50%, #581c87 100%);
        }
        
        .card-shadow {
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.1);
        }
        
        .protocol-card {
            transition: all 0.3s ease;
            border-left: 4px solid transparent;
        }
        
        .protocol-card:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(0, 0, 0, 0.15);
        }
        
        .protocol-card.cardiovascular {
            border-left-color: #dc2626;
            background: linear-gradient(135deg, #fef2f2 0%, #fefefe 100%);
        }
        
        .protocol-card.respiratory {
            border-left-color: #2563eb;
            background: linear-gradient(135deg, #eff6ff 0%, #fefefe 100%);
        }
        
        .protocol-card.digestive {
            border-left-color: #059669;
            background: linear-gradient(135deg, #ecfdf5 0%, #fefefe 100%);
        }
        
        .protocol-card.neurology {
            border-left-color: #7c3aed;
            background: linear-gradient(135deg, #f3e8ff 0%, #fefefe 100%);
        }
        
        .protocol-card.endocrine {
            border-left-color: #ea580c;
            background: linear-gradient(135deg, #fff7ed 0%, #fefefe 100%);
        }
        
        .protocol-card.renal {
            border-left-color: #0891b2;
            background: linear-gradient(135deg, #ecfeff 0%, #fefefe 100%);
        }
        
        .protocol-card.musculoskeletal {
            border-left-color: #65a30d;
            background: linear-gradient(135deg, #f7fee7 0%, #fefefe 100%);
        }
        
        .protocol-card.dermatology {
            border-left-color: #e11d48;
            background: linear-gradient(135deg, #fdf2f8 0%, #fefefe 100%);
        }
        
        .protocol-card.reproductive {
            border-left-color: #be185d;
            background: linear-gradient(135deg, #fdf2f8 0%, #fefefe 100%);
        }
        
        .protocol-card.hematology {
            border-left-color: #dc2626;
            background: linear-gradient(135deg, #fef2f2 0%, #fefefe 100%);
        }
        
        .protocol-card.infectious {
            border-left-color: #f59e0b;
            background: linear-gradient(135deg, #fffbeb 0%, #fefefe 100%);
        }
        
        .protocol-card.ophthalmology {
            border-left-color: #06b6d4;
            background: linear-gradient(135deg, #ecfeff 0%, #fefefe 100%);
        }
        
        .protocol-card.pediatric {
            border-left-color: #f472b6;
            background: linear-gradient(135deg, #fdf2f8 0%, #fefefe 100%);
        }
        
        .protocol-card.aesthetic {
            border-left-color: #ec4899;
            background: linear-gradient(135deg, #fdf2f8 0%, #fefefe 100%);
        }
        
        .protocol-card.allergen {
            border-left-color: #84cc16;
            background: linear-gradient(135deg, #f7fee7 0%, #fefefe 100%);
        }
        
        .protocol-card.chakra {
            border-left-color: #f59e0b;
            background: linear-gradient(135deg, #fef3c7 0%, #fefefe 100%);
        }
        
        .protocol-card.other {
            border-left-color: #6b7280;
            background: linear-gradient(135deg, #f9fafb 0%, #fefefe 100%);
        }
        
        .category-filter {
            transition: all 0.2s ease;
            border: 2px solid transparent;
        }
        
        .category-filter:hover {
            background-color: rgba(59, 130, 246, 0.1);
            border-color: rgba(59, 130, 246, 0.3);
        }
        
        .category-filter.active {
            background: linear-gradient(135deg, #3b82f6 0%, #1d4ed8 100%);
            color: white;
            border-color: #1d4ed8;
        }
        
        .fade-in {
            animation: fadeIn 0.5s ease-in;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }
    </style>
</head>
<body class="bg-gray-50 min-h-screen">
    <!-- Header -->
    <header class="gradient-bg text-white py-6 px-4">
        <div class="max-w-7xl mx-auto">
            <div class="flex items-center justify-between">
                <div>
                    <div class="text-blue-200 text-sm mb-2 font-medium">Created by Anavrin Wellness</div>
                    <h1 class="text-3xl font-bold flex items-center">
                        <span class="mr-3">🔬</span>
                        Bioplasm NLS V6 - Complete Protocol Database
                    </h1>
                    <p class="text-blue-100 mt-2">Professional NLS Scanning Protocols with Detailed System Analysis</p>
                </div>
                <div class="bg-green-100 text-green-800 rounded-lg p-4">
                    <div class="text-sm">Database Status</div>
                    <div class="text-2xl font-bold">Ready</div>
                    <div class="text-xs">800+ Protocols</div>
                </div>
            </div>
        </div>
    </header>

    <div class="max-w-7xl mx-auto px-4 py-8">
        <div class="grid grid-cols-1 lg:grid-cols-4 gap-8">
            <!-- Sidebar Controls -->
            <div class="space-y-6">
                <!-- Search -->
                <div class="bg-white rounded-xl card-shadow p-6">
                    <h3 class="text-lg font-semibold text-gray-800 mb-4 flex items-center">
                        <span class="mr-2">🔍</span>
                        Search Protocols
                    </h3>
                    <input 
                        type="text" 
                        id="searchInput" 
                        class="w-full p-3 border border-gray-300 rounded-lg focus:ring-2 focus:ring-blue-500 focus:border-transparent"
                        placeholder="Search conditions..."
                        onkeyup="searchProtocols()"
                    >
                </div>

                <!-- Category Filters -->
                <div class="bg-white rounded-xl card-shadow p-6">
                    <h3 class="text-lg font-semibold text-gray-800 mb-4 flex items-center">
                        <span class="mr-2">📂</span>
                        Medical Categories
                    </h3>
                    <div class="space-y-2" id="categoryFilters">
                        <button onclick="filterByCategory('all')" class="category-filter active w-full text-left px-3 py-2 rounded-lg text-sm font-medium">All Categories</button>
                        <button onclick="filterByCategory('cardiovascular')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">❤️ Cardiovascular</button>
                        <button onclick="filterByCategory('respiratory')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">🫁 Respiratory & ENT</button>
                        <button onclick="filterByCategory('digestive')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">🍽️ Digestive System</button>
                        <button onclick="filterByCategory('neurology')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">🧠 Neurology & CNS</button>
                        <button onclick="filterByCategory('endocrine')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">⚡ Endocrine</button>
                        <button onclick="filterByCategory('renal')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">🔵 Renal & Urinary</button>
                        <button onclick="filterByCategory('musculoskeletal')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">🦴 Musculoskeletal</button>
                        <button onclick="filterByCategory('dermatology')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">🌸 Dermatology</button>
                        <button onclick="filterByCategory('reproductive')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">👥 Reproductive</button>
                        <button onclick="filterByCategory('hematology')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">🩸 Hematology</button>
                        <button onclick="filterByCategory('infectious')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">🦠 Infectious Diseases</button>
                        <button onclick="filterByCategory('ophthalmology')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">👁️ Ophthalmology</button>
                        <button onclick="filterByCategory('pediatric')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">👶 Pediatric</button>
                        <button onclick="filterByCategory('aesthetic')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">✨ Aesthetic</button>
                        <button onclick="filterByCategory('allergen')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">🌾 Allergen Testing</button>
                        <button onclick="filterByCategory('chakra')" class="category-filter w-full text-left px-3 py-2 rounded-lg text-sm font-medium">🕉️ Chakra & Aura</button>
                    </div>
                </div>
            </div>

            <!-- Main Protocol Display -->
            <div class="lg:col-span-3">
                <div class="bg-white rounded-xl card-shadow p-6">
                    <div class="flex justify-between items-center mb-6">
                        <h2 class="text-2xl font-semibold text-gray-800 flex items-center">
                            <span class="mr-3">📋</span>
                            NLS Protocol Database
                        </h2>
                        <div class="flex items-center space-x-4">
                            <span class="text-sm text-gray-600">Showing: <span id="resultCount">0</span> protocols</span>
                        </div>
                    </div>
                    
                    <div id="protocolGrid" class="grid grid-cols-1 md:grid-cols-2 gap-4">
                        <!-- Protocols will be loaded here -->
                    </div>
                    
                    <div id="noResults" class="text-center py-12 hidden">
                        <div class="text-gray-400 text-6xl mb-4">🔍</div>
                        <h3 class="text-lg font-semibold text-gray-600 mb-2">No protocols found</h3>
                        <p class="text-gray-500">Try adjusting your search or filter criteria.</p>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Protocol Detail Modal -->
    <div id="protocolModal" class="fixed inset-0 bg-black bg-opacity-50 hidden z-50 flex items-center justify-center p-4">
        <div class="bg-white rounded-xl max-w-6xl w-full max-h-[90vh] overflow-y-auto">
            <div class="p-6">
                <div class="flex justify-between items-start mb-4">
                    <h3 class="text-2xl font-bold text-gray-800" id="modalTitle"></h3>
                    <button onclick="closeModal()" class="text-gray-500 hover:text-gray-700 text-2xl">&times;</button>
                </div>
                <div id="modalContent"></div>
            </div>
        </div>
    </div>

    <script>
        // Comprehensive medical conditions database
        const medicalConditions = [
            // Cardiovascular
            "Hypertension", "Myocardial infarction", "Angina pectoris", "Atrial fibrillation", "Heart failure",
            "Cardiomyopathy", "Pericarditis", "Endocarditis", "Aortic stenosis", "Mitral regurgitation",
            "Pulmonary embolism", "Deep vein thrombosis", "Peripheral artery disease", "Aortic aneurysm",
            "Cardiac arrhythmia", "Bradycardia", "Tachycardia", "Ventricular fibrillation", "Heart block",
            "Coronary artery disease", "Atherosclerosis", "Varicose veins", "Thrombophlebitis",
            
            // Respiratory & ENT
            "Pneumonia", "Asthma", "Chronic obstructive pulmonary disease", "Bronchitis", "Tuberculosis",
            "Lung cancer", "Pleural effusion", "Pneumothorax", "Pulmonary fibrosis", "Sleep apnea",
            "Emphysema", "Bronchiectasis", "Sarcoidosis", "Pulmonary hypertension", "Respiratory failure",
            "Tinnitus", "Hearing loss", "Vertigo", "Meniere's disease", "Otitis media", "Sinusitis",
            "Rhinitis", "Laryngitis", "Pharyngitis", "Tonsillitis",
            
            // Digestive System
            "Gastroesophageal reflux disease", "Peptic ulcer", "Inflammatory bowel disease", "Crohn's disease",
            "Ulcerative colitis", "Irritable bowel syndrome", "Gastritis", "Hepatitis", "Cirrhosis",
            "Pancreatitis", "Gallstones", "Appendicitis", "Diverticulitis", "Celiac disease",
            "Gastroenteritis", "Constipation", "Diarrhea", "Hemorrhoids", "Liver cancer",
            
            // Neurology & CNS
            "Stroke", "Migraine", "Epilepsy", "Parkinson's disease", "Alzheimer's disease", "Multiple sclerosis",
            "Meningitis", "Encephalitis", "Brain tumor", "Spinal cord injury", "Peripheral neuropathy",
            "Trigeminal neuralgia", "Bell's palsy", "Guillain-Barré syndrome", "Myasthenia gravis",
            "Huntington's disease", "Amyotrophic lateral sclerosis", "Cerebral palsy", "Hydrocephalus",
            "Concussion", "Dementia", "Headache", "Sciatica", "Carpal tunnel syndrome",
            
            // Mental Health Disorders
            "Bipolar Disorder", "Schizophrenia", "Dissociative Identity Disorder", "Multiple Personality Disorder",
            
            // Endocrine
            "Diabetes mellitus type 1", "Diabetes mellitus type 2", "Hyperthyroidism", "Hypothyroidism",
            "Thyroid cancer", "Adrenal insufficiency", "Cushing's syndrome", "Hyperparathyroidism",
            "Hypoparathyroidism", "Pituitary adenoma", "Growth hormone deficiency", "Diabetes insipidus",
            "Polycystic ovary syndrome", "Metabolic syndrome", "Obesity", "Osteoporosis",
            
            // Renal & Urinary
            "Urinary tract infection", "Kidney stones", "Chronic kidney disease", "Acute kidney injury",
            "Bladder cancer", "Kidney cancer", "Prostate cancer", "Benign prostatic hyperplasia",
            "Erectile dysfunction", "Urinary incontinence", "Interstitial cystitis", "Pyelonephritis",
            "Glomerulonephritis", "Nephrotic syndrome", "Polycystic kidney disease", "Renal failure",
            
            // Musculoskeletal
            "Osteoarthritis", "Rheumatoid arthritis", "Fibromyalgia", "Osteoporosis", "Fracture",
            "Spinal stenosis", "Herniated disc", "Scoliosis", "Tendinitis", "Bursitis", "Gout",
            "Lupus", "Ankylosing spondylitis", "Rotator cuff tear", "Plantar fasciitis", "Back pain",
            
            // Dermatology
            "Eczema", "Psoriasis", "Acne", "Melanoma", "Basal cell carcinoma", "Squamous cell carcinoma",
            "Dermatitis", "Urticaria", "Vitiligo", "Alopecia", "Fungal infection", "Cellulitis",
            "Herpes simplex", "Rosacea", "Seborrheic dermatitis", "Contact dermatitis",
            
            // Reproductive
            "Endometriosis", "Uterine fibroids", "Ovarian cysts", "Cervical cancer", "Ovarian cancer",
            "Endometrial cancer", "Breast cancer", "Mastitis", "Fibrocystic breast disease",
            "Pelvic inflammatory disease", "Sexually transmitted infections", "Infertility",
            "Menstrual disorders", "Menopause", "Pregnancy complications", "Prostatitis",
            
            // Hematology
            "Anemia", "Iron deficiency anemia", "Sickle cell disease", "Thalassemia", "Leukemia",
            "Lymphoma", "Multiple myeloma", "Thrombocytopenia", "Hemophilia", "Von Willebrand disease",
            
            // Infectious Diseases
            "Influenza", "Common cold", "COVID-19", "Sepsis", "Abscess", "Osteomyelitis",
            "HIV/AIDS", "Malaria", "Dengue fever", "Hepatitis A", "Hepatitis B", "Hepatitis C",
            
            // Ophthalmology
            "Cataracts", "Glaucoma", "Macular degeneration", "Diabetic retinopathy", "Retinal detachment",
            "Conjunctivitis", "Dry eye syndrome", "Stye", "Corneal ulcer", "Uveitis",
            
            // Pediatric
            "Congenital heart defects", "Respiratory distress syndrome", "Neonatal jaundice",
            "Failure to thrive", "Developmental delays", "Pediatric asthma", "Childhood obesity",
            "Attention deficit hyperactivity disorder", "Autism spectrum disorders", "Juvenile diabetes",
            
            // Aesthetic Procedures
            "Skin Rejuvenation (Anti-Aging / Wrinkle Reduction)", "Weight Management / Cellulite Reduction", 
            "Hair Strength & Growth Support", "Skin Detox & Acne Protocol", "Scar & Stretch Mark Regeneration",
            "Body contouring", "Stretch mark reduction", "Scar tissue remodeling", "Facial tightening", "Collagen stimulation",
            
            // Allergen Testing - Food Allergens
            "Milk allergy", "Egg allergy", "Peanut allergy", "Tree nut allergy", "Soy allergy",
            "Wheat allergy", "Fish allergy", "Shellfish allergy", "Sesame allergy", "Corn allergy",
            "Chocolate allergy", "Strawberry allergy", "Tomato allergy", "Citrus allergy", "Apple allergy",
            "Banana allergy", "Kiwi allergy", "Mango allergy", "Peach allergy", "Grape allergy",
            "Carrot allergy", "Celery allergy", "Onion allergy", "Garlic allergy", "Potato allergy",
            "Rice allergy", "Oat allergy", "Barley allergy", "Rye allergy", "Buckwheat allergy",
            "Quinoa allergy", "Sunflower seed allergy", "Pumpkin seed allergy", "Mustard allergy",
            "Honey allergy", "Yeast allergy", "Food additive allergy", "Artificial color allergy",
            "Preservative allergy", "MSG allergy", "Sulfite allergy", "Nitrate allergy",
            
            // Allergen Testing - Environmental Allergens
            "Dust mite allergy", "Pet dander allergy", "Cat allergy", "Dog allergy", "Horse allergy",
            "Rabbit allergy", "Bird feather allergy", "Cockroach allergy", "Mold allergy",
            "Aspergillus allergy", "Penicillium allergy", "Cladosporium allergy", "Alternaria allergy",
            "Candida allergy", "Latex allergy", "Nickel allergy", "Chromium allergy", "Cobalt allergy",
            "Formaldehyde allergy", "Perfume allergy", "Fabric softener allergy", "Detergent allergy",
            "Cleaning product allergy", "Paint fume allergy", "Cigarette smoke allergy",
            
            // Allergen Testing - Pollen Allergens
            "Grass pollen allergy", "Tree pollen allergy", "Weed pollen allergy", "Ragweed allergy",
            "Birch pollen allergy", "Oak pollen allergy", "Maple pollen allergy", "Pine pollen allergy",
            "Cedar pollen allergy", "Elm pollen allergy", "Ash pollen allergy", "Hickory pollen allergy",
            "Timothy grass allergy", "Bermuda grass allergy", "Johnson grass allergy", "Orchard grass allergy",
            "Rye grass allergy", "Fescue grass allergy", "Bluegrass allergy", "Plantain allergy",
            "Dandelion allergy", "Mugwort allergy", "Sagebrush allergy", "Lamb's quarters allergy",
            
            // Allergen Testing - Chemical Allergens
            "Pesticide allergy", "Herbicide allergy", "Insecticide allergy", "Chlorine allergy",
            "Fluoride allergy", "Benzene allergy", "Toluene allergy", "Xylene allergy",
            "Ammonia allergy", "Bleach allergy", "Alcohol allergy", "Acetone allergy",
            "Petroleum product allergy", "Plastic allergy", "Rubber allergy", "Adhesive allergy",
            
            // Allergen Testing - Drug Allergens
            "Penicillin allergy", "Aspirin allergy", "Ibuprofen allergy", "Acetaminophen allergy",
            "Codeine allergy", "Morphine allergy", "Insulin allergy", "Vaccine allergy",
            "Anesthetic allergy", "Contrast dye allergy", "Antibiotic allergy", "Steroid allergy",
            
            // Allergen Testing - Insect/Venom Allergens
            "Bee sting allergy", "Wasp sting allergy", "Hornet sting allergy", "Yellow jacket allergy",
            "Fire ant allergy", "Mosquito bite allergy", "Flea bite allergy", "Spider bite allergy",
            
            // Chakra & Aura Protocols
            "Root Chakra Balancing", "Sacral Chakra Healing", "Solar Plexus Empowerment", "Heart Chakra Opening",
            "Throat Chakra Clearing", "Third Eye Activation", "Crown Chakra Connection", "Full Chakra Alignment",
            "Aura Cleansing", "Energy Field Repair", "Biofield Harmonization"
        ];

        // Global variables
        let currentFilter = 'all';
        let allProtocols = [];

        // Categorization rules
        const categoryRules = [
            ["cardiovascular", /(heart|cardiac|cardio|myocardial|coronary|aortic|arterial|hypertension|hypotension|arrhythmia|tachycardia|bradycardia|angina|atherosclerosis|thrombosis|embolism|aneurysm|valve|pericarditis|endocarditis|cardiomyopathy|varicose|thrombophlebitis)/i],
            ["respiratory", /(lung|pulmonary|bronch|pneumo|respiratory|asthma|cough|dyspnea|pleura|emphysema|tuberculosis|pneumonia|tinnitus|hearing|ear|otitis|vertigo|meniere|sinusitis|rhinitis|laryngitis|pharyngitis|tonsillitis)/i],
            ["digestive", /(gastro|stomach|intestin|liver|hepatic|pancrea|gallbladder|colon|digestive|ulcer|reflux|crohn|colitis|ibs|gastritis|hepatitis|cirrhosis|pancreatitis|gallstones|appendicitis|diverticulitis|celiac|hemorrhoids)/i],
            ["neurology", /(brain|cerebr|neural|neuro|spinal|stroke|migraine|epilepsy|parkinson|alzheimer|sclerosis|meningitis|encephalitis|neuropathy|neuralgia|palsy|guillain|myasthenia|huntington|als|cerebral|hydrocephalus|concussion|dementia|headache|sciatica|carpal tunnel|bipolar|schizophrenia|dissociative|multiple personality)/i],
            ["endocrine", /(diabetes|thyroid|adrenal|pituitary|hormone|insulin|glucose|metabolic|obesity|osteoporosis|cushing|parathyroid|growth hormone|polycystic ovary)/i],
            ["renal", /(kidney|renal|urinary|bladder|prostate|urine|nephro|glomerulo|ureter|urethra|incontinence|cystitis|pyelonephritis|stones)/i],
            ["musculoskeletal", /(bone|joint|arthritis|osteo|muscle|tendon|ligament|cartilage|spine|vertebr|spondyl|fracture|fibromyalgia|bursitis|gout|lupus|scoliosis|disc|stenosis|rotator cuff|plantar fasciitis|back pain)/i],
            ["dermatology", /(skin|dermat|eczema|psoriasis|acne|melanoma|carcinoma|rash|urticaria|vitiligo|alopecia|fungal|cellulitis|herpes|rosacea|seborrheic|contact)/i],
            ["reproductive", /(endometriosis|uterine|ovarian|cervical|breast|mastitis|fibrocystic|pelvic inflammatory|sexually transmitted|infertility|menstrual|menopause|pregnancy|prostatitis)/i],
            ["hematology", /(anemia|sickle cell|thalassemia|leukemia|lymphoma|myeloma|thrombocytopenia|hemophilia|von willebrand|blood)/i],
            ["infectious", /(infection|sepsis|abscess|osteomyelitis|influenza|cold|covid|hiv|aids|malaria|dengue|hepatitis)/i],
            ["ophthalmology", /(eye|cataract|glaucoma|macular|retinal|conjunctivitis|dry eye|stye|corneal|uveitis|vision)/i],
            ["pediatric", /(congenital|neonatal|pediatric|childhood|juvenile|developmental|failure to thrive|adhd|autism)/i],
            ["aesthetic", /(weight loss|cellulite|skin tightening|wrinkle|facial rejuvenation|body contouring|anti-aging|collagen|stretch mark|scar tissue|hair growth)/i],
            ["allergen", /(allergy|allergen|milk|egg|peanut|tree nut|soy|wheat|fish|shellfish|sesame|corn|chocolate|strawberry|tomato|citrus|apple|banana|kiwi|mango|peach|grape|carrot|celery|onion|garlic|potato|rice|oat|barley|rye|buckwheat|quinoa|sunflower|pumpkin|mustard|honey|yeast|additive|color|preservative|msg|sulfite|nitrate|dust mite|pet dander|cat|dog|horse|rabbit|bird feather|cockroach|mold|aspergillus|penicillium|cladosporium|alternaria|candida|latex|nickel|chromium|cobalt|formaldehyde|perfume|fabric softener|detergent|cleaning|paint fume|cigarette smoke|grass pollen|tree pollen|weed pollen|ragweed|birch pollen|oak pollen|maple pollen|pine pollen|cedar pollen|elm pollen|ash pollen|hickory pollen|timothy grass|bermuda grass|johnson grass|orchard grass|rye grass|fescue grass|bluegrass|plantain|dandelion|mugwort|sagebrush|lamb's quarters|pesticide|herbicide|insecticide|chlorine|fluoride|benzene|toluene|xylene|ammonia|bleach|alcohol|acetone|petroleum|plastic|rubber|adhesive|penicillin|aspirin|ibuprofen|acetaminophen|codeine|morphine|insulin|vaccine|anesthetic|contrast dye|antibiotic|steroid|bee sting|wasp sting|hornet sting|yellow jacket|fire ant|mosquito bite|flea bite|spider bite)/i],
            ["chakra", /(chakra|aura|energy field|biofield)/i],
            ["other", /./]
        ];

        // Get detailed systems to scan for each condition
        function getDetailedSystemsToScan(condition, category) {
            const conditionLower = condition.toLowerCase();
            
            // Tinnitus (your blueprint example)
            if (conditionLower.includes('tinnitus')) {
                return {
                    'ENT': 'Inner ear, cochlea, auditory nerve, vestibular system',
                    'Neurological': 'Brainstem auditory centers, temporal lobe, cranial nerves',
                    'Cardiovascular': 'Carotid arteries, microcirculation, hypertension profiles',
                    'Metabolic/Endocrine': 'Thyroid, adrenal stress response',
                    'Psychological': 'Stress, anxiety, sleep centers'
                };
            }
            
            // Cardiovascular conditions
            else if (category === 'cardiovascular') {
                if (conditionLower.includes('hypertension')) {
                    return {
                        'Cardiovascular': 'Heart chambers, aorta, coronary arteries, cardiac valves, myocardium',
                        'Renal': 'Kidneys, renal arteries, glomeruli, renin-angiotensin system',
                        'Neurological': 'Autonomic nervous system, baroreceptors, vasomotor centers',
                        'Endocrine': 'Adrenal glands, aldosterone pathways, thyroid function',
                        'Vascular': 'Peripheral vessels, arterial walls, endothelium, microcirculation'
                    };
                } else if (conditionLower.includes('myocardial infarction') || conditionLower.includes('heart attack')) {
                    return {
                        'Cardiovascular': 'Myocardium, coronary circulation, cardiac conduction system, pericardium',
                        'Respiratory': 'Lungs, pulmonary circulation, oxygen transport, gas exchange',
                        'Coagulation': 'Platelet function, coagulation cascade, fibrinolytic system',
                        'Metabolic': 'Cellular energy production, mitochondrial function, lactate metabolism',
                        'Inflammatory': 'Cytokine pathways, inflammatory markers, tissue repair mechanisms'
                    };
                } else if (conditionLower.includes('arrhythmia') || conditionLower.includes('fibrillation')) {
                    return {
                        'Cardiovascular': 'SA node, AV node, bundle branches, Purkinje fibers, myocardium',
                        'Electrolyte': 'Sodium channels, potassium channels, calcium channels, magnesium balance',
                        'Neurological': 'Autonomic nervous system, vagal tone, sympathetic activity',
                        'Endocrine': 'Thyroid function, adrenal activity, stress hormones',
                        'Metabolic': 'ATP production, ion pump function, cellular energy metabolism'
                    };
                } else {
                    return {
                        'Cardiovascular': 'Heart, coronary arteries, cardiac valves, myocardium, pericardium',
                        'Circulatory': 'Peripheral vessels, venous system, lymphatics, microcirculation',
                        'Respiratory': 'Pulmonary circulation, gas exchange, oxygen transport',
                        'Renal': 'Kidney function, fluid balance, electrolyte regulation',
                        'Neurological': 'Cardiac reflexes, autonomic control, baroreceptors'
                    };
                }
            }
            
            // Respiratory conditions
            else if (category === 'respiratory') {
                if (conditionLower.includes('asthma')) {
                    return {
                        'Respiratory': 'Bronchi, bronchioles, alveoli, respiratory muscles, pleura',
                        'Immune': 'Mast cells, eosinophils, IgE pathways, inflammatory mediators',
                        'Allergic': 'Allergen recognition, histamine release, complement activation',
                        'Neurological': 'Vagal control, respiratory centers, autonomic reflexes',
                        'Endocrine': 'Adrenal function, cortisol response, stress adaptation'
                    };
                } else if (conditionLower.includes('pneumonia')) {
                    return {
                        'Respiratory': 'Alveoli, bronchi, lung parenchyma, pleural space, airways',
                        'Immune': 'Macrophages, neutrophils, complement system, antibodies',
                        'Infectious': 'Bacterial pathogens, viral agents, fungal organisms',
                        'Inflammatory': 'Cytokine response, inflammatory markers, tissue damage',
                        'Cardiovascular': 'Pulmonary circulation, oxygenation, cardiac compensation'
                    };
                } else if (conditionLower.includes('copd') || conditionLower.includes('emphysema')) {
                    return {
                        'Respiratory': 'Alveolar walls, bronchioles, respiratory muscles, diaphragm',
                        'Inflammatory': 'Chronic inflammation, protease activity, oxidative stress',
                        'Cardiovascular': 'Pulmonary hypertension, right heart function, cor pulmonale',
                        'Metabolic': 'Oxygen utilization, CO2 retention, acid-base balance',
                        'Muscular': 'Respiratory muscle fatigue, accessory muscles, chest wall mechanics'
                    };
                } else {
                    return {
                        'Respiratory': 'Lungs, bronchi, trachea, alveoli, pleura, respiratory muscles',
                        'Cardiovascular': 'Pulmonary circulation, right heart, oxygenation pathways',
                        'Immune': 'Respiratory immunity, mucosal barriers, pathogen clearance',
                        'Neurological': 'Respiratory control centers, vagal innervation, reflexes',
                        'Infectious': 'Antimicrobial defenses, barrier function, clearance mechanisms'
                    };
                }
            }
            
            // Digestive conditions
            else if (category === 'digestive') {
                if (conditionLower.includes('gastritis') || conditionLower.includes('ulcer')) {
                    return {
                        'Digestive': 'Stomach mucosa, gastric glands, pyloric sphincter, duodenum',
                        'Infectious': 'H. pylori, bacterial overgrowth, pathogen identification',
                        'Immune': 'Mucosal immunity, inflammatory response, autoimmune markers',
                        'Neurological': 'Vagal control, enteric nervous system, stress pathways',
                        'Vascular': 'Gastric blood flow, mucosal perfusion, healing factors'
                    };
                } else if (conditionLower.includes('liver') || conditionLower.includes('hepat')) {
                    return {
                        'Hepatic': 'Hepatocytes, bile ducts, portal circulation, liver lobules',
                        'Metabolic': 'Detoxification pathways, protein synthesis, glucose metabolism',
                        'Immune': 'Kupffer cells, autoimmune markers, inflammatory cytokines',
                        'Vascular': 'Portal vein, hepatic artery, sinusoids, venous drainage',
                        'Biliary': 'Gallbladder, bile ducts, bile composition, flow dynamics'
                    };
                } else if (conditionLower.includes('ibs') || conditionLower.includes('irritable')) {
                    return {
                        'Digestive': 'Small intestine, colon, enteric nervous system, gut motility',
                        'Neurological': 'Gut-brain axis, vagal tone, stress response, pain pathways',
                        'Microbiome': 'Gut bacteria, dysbiosis, SIBO, fermentation patterns',
                        'Immune': 'Mucosal immunity, food sensitivities, inflammatory markers',
                        'Psychological': 'Stress centers, anxiety pathways, mood regulation'
                    };
                } else {
                    return {
                        'Digestive': 'Stomach, small intestine, large intestine, pancreas, liver',
                        'Microbiome': 'Gut bacteria, bacterial balance, dysbiosis, pathogen overgrowth',
                        'Immune': 'GALT, mucosal immunity, food sensitivities, inflammatory response',
                        'Neurological': 'Enteric nervous system, gut-brain axis, vagal control',
                        'Metabolic': 'Enzyme production, nutrient absorption, energy metabolism'
                    };
                }
            }
            
            // Neurological conditions
            else if (category === 'neurology') {
                if (conditionLower.includes('bipolar')) {
                    return {
                        'Neurological': 'Prefrontal cortex, limbic system (amygdala, hippocampus), basal ganglia',
                        'Endocrine': 'Thyroid function, adrenal cortisol, pineal gland melatonin',
                        'Neurotransmitters': 'Dopamine pathways, serotonin receptors, GABA systems',
                        'Detoxification': 'Heavy metals, drug residues, alcohol metabolites',
                        'Energy Centers': 'Solar plexus chakra, third eye chakra, aura field stability'
                    };
                } else if (conditionLower.includes('schizophrenia')) {
                    return {
                        'Neurological': 'Frontal lobes, temporal lobes, hippocampus, thalamus',
                        'Neurotransmitters': 'Dopamine excess, glutamate receptors, serotonin balance',
                        'Immune/Inflammatory': 'Microglial activation, viral/bacterial triggers, cytokines',
                        'Endocrine': 'Pineal gland melatonin, adrenal stress response',
                        'Energy Centers': 'Crown chakra, third eye chakra, aura fragmentation patterns'
                    };
                } else if (conditionLower.includes('dissociative') || conditionLower.includes('multiple personality')) {
                    return {
                        'Neurological': 'Prefrontal cortex, hippocampus, amygdala, memory centers',
                        'Psychological': 'Trauma patterns, subconscious resonance, dissociative states',
                        'Endocrine': 'Stress axis (adrenal, cortisol, norepinephrine)',
                        'Energy Centers': 'Root chakra (safety), solar plexus (identity), crown (integration)',
                        'Trauma Pathways': 'PTSD markers, emotional memory circuits, stress responses'
                    };
                } else if (conditionLower.includes('alzheimer') || conditionLower.includes('dementia')) {
                    return {
                        'Neurological': 'Cerebral cortex, hippocampus, temporal lobe, frontal lobe',
                        'Vascular': 'Cerebral circulation, blood-brain barrier, microvascular health',
                        'Metabolic': 'Glucose metabolism, mitochondrial function, energy production',
                        'Inflammatory': 'Neuroinflammation, microglial activation, cytokine response',
                        'Protein': 'Amyloid processing, tau protein, protein aggregation pathways'
                    };
                } else if (conditionLower.includes('parkinson')) {
                    return {
                        'Neurological': 'Substantia nigra, basal ganglia, dopaminergic pathways',
                        'Motor': 'Motor cortex, cerebellum, movement coordination centers',
                        'Neurotransmitter': 'Dopamine synthesis, receptors, reuptake mechanisms',
                        'Mitochondrial': 'Cellular energy, oxidative stress, neuroprotection',
                        'Inflammatory': 'Neuroinflammation, microglial response, protein aggregation'
                    };
                } else if (conditionLower.includes('stroke')) {
                    return {
                        'Neurological': 'Affected brain regions, penumbra, neural plasticity areas',
                        'Vascular': 'Cerebral arteries, collateral circulation, blood flow dynamics',
                        'Coagulation': 'Clotting factors, platelet function, fibrinolytic system',
                        'Inflammatory': 'Acute phase response, cytokines, tissue damage markers',
                        'Recovery': 'Neuroplasticity, stem cell activation, repair mechanisms'
                    };
                } else if (conditionLower.includes('migraine')) {
                    return {
                        'Neurological': 'Trigeminal system, brainstem, cortical spreading depression',
                        'Vascular': 'Cerebral vessels, vasodilation/constriction, blood flow',
                        'Neurotransmitter': 'Serotonin, CGRP, dopamine, norepinephrine pathways',
                        'Hormonal': 'Estrogen fluctuations, stress hormones, circadian rhythms',
                        'Inflammatory': 'Neurogenic inflammation, mast cell activation, pain pathways'
                    };
                } else {
                    return {
                        'Neurological': 'Brain, spinal cord, peripheral nerves, cranial nerves',
                        'Vascular': 'Cerebral circulation, blood-brain barrier, neural perfusion',
                        'Neurotransmitter': 'Synaptic function, neurotransmitter balance, receptors',
                        'Inflammatory': 'Neuroinflammation, glial cells, immune response',
                        'Metabolic': 'Neural energy, glucose utilization, mitochondrial function'
                    };
                }
            }
            
            // Endocrine conditions
            else if (category === 'endocrine') {
                if (conditionLower.includes('diabetes')) {
                    return {
                        'Endocrine': 'Pancreatic islets, beta cells, insulin pathways, glucagon',
                        'Metabolic': 'Glucose metabolism, lipid metabolism, protein synthesis',
                        'Vascular': 'Microvascular complications, endothelial function, circulation',
                        'Renal': 'Kidney function, diabetic nephropathy, filtration capacity',
                        'Neurological': 'Diabetic neuropathy, autonomic function, pain pathways'
                    };
                } else if (conditionLower.includes('thyroid')) {
                    return {
                        'Endocrine': 'Thyroid gland, TSH pathways, T3/T4 production, iodine metabolism',
                        'Metabolic': 'Basal metabolic rate, energy production, thermogenesis',
                        'Cardiovascular': 'Heart rate, cardiac output, vascular resistance',
                        'Neurological': 'Cognitive function, mood regulation, reflexes',
                        'Immune': 'Autoimmune markers, thyroid antibodies, inflammatory response'
                    };
                } else {
                    return {
                        'Endocrine': 'Pituitary, thyroid, adrenals, pancreas, gonads, parathyroid',
                        'Metabolic': 'Hormone synthesis, receptor function, feedback loops',
                        'Neurological': 'Hypothalamic control, circadian rhythms, stress response',
                        'Cardiovascular': 'Hormone effects on heart, vessels, blood pressure',
                        'Reproductive': 'Sex hormone pathways, fertility, reproductive organs'
                    };
                }
            }
            
            // Renal conditions
            else if (category === 'renal') {
                return {
                    'Renal': 'Kidneys, glomeruli, tubules, collecting ducts, renal pelvis',
                    'Urinary': 'Ureters, bladder, urethra, sphincters, pelvic floor',
                    'Cardiovascular': 'Renal circulation, blood pressure regulation, fluid balance',
                    'Endocrine': 'Renin-angiotensin system, aldosterone, ADH pathways',
                    'Electrolyte': 'Sodium, potassium, calcium, phosphorus, acid-base balance'
                };
            }
            
            // Musculoskeletal conditions
            else if (category === 'musculoskeletal') {
                return {
                    'Skeletal': 'Bones, joints, cartilage, synovial membranes, ligaments',
                    'Muscular': 'Skeletal muscles, tendons, fascia, muscle fibers',
                    'Neurological': 'Motor neurons, neuromuscular junctions, reflexes',
                    'Vascular': 'Blood supply to bones, muscles, joint circulation',
                    'Inflammatory': 'Inflammatory markers, autoimmune responses, cytokines'
                };
            }
            
            // Dermatology conditions
            else if (category === 'dermatology') {
                return {
                    'Integumentary': 'Epidermis, dermis, subcutaneous tissue, hair follicles',
                    'Immune': 'Skin immunity, allergic responses, inflammatory pathways',
                    'Vascular': 'Skin circulation, capillary beds, lymphatic drainage',
                    'Neurological': 'Sensory nerves, pain receptors, itch pathways',
                    'Metabolic': 'Skin barrier function, sebaceous glands, sweat glands'
                };
            }
            
            // Reproductive conditions
            else if (category === 'reproductive') {
                return {
                    'Reproductive': 'Gonads, reproductive tract, external genitalia',
                    'Endocrine': 'Sex hormones, pituitary-gonadal axis, feedback loops',
                    'Vascular': 'Reproductive organ circulation, erectile function',
                    'Neurological': 'Sexual function pathways, autonomic control',
                    'Immune': 'Reproductive immunity, autoimmune factors, infections'
                };
            }
            
            // Hematology conditions
            else if (category === 'hematology') {
                return {
                    'Hematopoietic': 'Bone marrow, stem cells, blood cell production',
                    'Circulatory': 'Blood vessels, circulation, hemodynamics',
                    'Coagulation': 'Clotting factors, platelets, fibrinolytic system',
                    'Immune': 'White blood cells, lymphoid organs, immune function',
                    'Metabolic': 'Iron metabolism, B12/folate pathways, hemoglobin synthesis'
                };
            }
            
            // Infectious diseases
            else if (category === 'infectious') {
                return {
                    'Immune': 'Immune system, white blood cells, antibody production',
                    'Pathogen': 'Bacterial, viral, fungal, parasitic identification',
                    'Inflammatory': 'Inflammatory response, cytokines, acute phase proteins',
                    'Barrier': 'Mucosal barriers, skin integrity, natural defenses',
                    'Systemic': 'Organ involvement, sepsis pathways, toxin effects'
                };
            }
            
            // Ophthalmology conditions
            else if (category === 'ophthalmology') {
                return {
                    'Ocular': 'Cornea, lens, retina, vitreous, optic nerve, extraocular muscles',
                    'Neurological': 'Visual pathways, optic nerve, visual cortex',
                    'Vascular': 'Retinal circulation, choroidal blood flow, ocular perfusion',
                    'Inflammatory': 'Ocular inflammation, autoimmune responses, infections',
                    'Metabolic': 'Aqueous humor dynamics, intraocular pressure, glucose effects'
                };
            }
            
            // Pediatric conditions
            else if (category === 'pediatric') {
                return {
                    'Developmental': 'Growth centers, developmental milestones, maturation',
                    'Immune': 'Developing immune system, vaccination responses, infections',
                    'Neurological': 'Brain development, neural plasticity, cognitive development',
                    'Endocrine': 'Growth hormones, pubertal development, metabolic maturation',
                    'Nutritional': 'Nutrient absorption, growth requirements, feeding patterns'
                };
            }
            
            // Aesthetic procedures
            else if (category === 'aesthetic') {
                if (conditionLower.includes('skin rejuvenation') || conditionLower.includes('anti-aging') || conditionLower.includes('wrinkle')) {
                    return {
                        'Integumentary': 'Epidermis, dermis, collagen matrix, elastin fibers, hyaluronic acid',
                        'Circulatory': 'Capillaries, microcirculation, tissue perfusion, oxygen delivery',
                        'Endocrine': 'Estrogen pathways, thyroid function, adrenal stress hormones',
                        'Detoxification': 'Liver phase I/II, lymphatic drainage, kidney filtration',
                        'Cellular': 'Fibroblasts, keratinocytes, mitochondrial function, ATP production'
                    };
                } else if (conditionLower.includes('weight') || conditionLower.includes('cellulite')) {
                    return {
                        'Adipose Tissue': 'Subcutaneous fat, brown fat, adipocytes, lipid metabolism',
                        'Endocrine': 'Thyroid function, pancreatic insulin, adrenal cortisol',
                        'Circulatory': 'Lymphatic vessels, venous return, microcirculation',
                        'Digestive': 'Liver detoxification, gut microbiome, metabolic pathways',
                        'Metabolic': 'Lipolysis, thermogenesis, energy expenditure, fat oxidation'
                    };
                } else if (conditionLower.includes('hair')) {
                    return {
                        'Integumentary': 'Scalp tissue, hair follicles, sebaceous glands, keratinocytes',
                        'Endocrine': 'Thyroid hormones, androgens, DHT metabolism, adrenal stress',
                        'Circulatory': 'Scalp microcirculation, follicular blood supply, oxygen delivery',
                        'Nutritional': 'Iron metabolism, zinc pathways, protein synthesis, B vitamins',
                        'Cellular': 'Hair cycle phases, keratin production, follicle stem cells'
                    };
                } else if (conditionLower.includes('acne') || conditionLower.includes('detox')) {
                    return {
                        'Integumentary': 'Sebaceous glands, pores, dermis, epidermis, hair follicles',
                        'Microorganisms': 'P. acnes, Candida albicans, Staphylococcus aureus, skin microbiome',
                        'Detoxification': 'Liver phase I/II, kidney filtration, colon elimination, lymphatic drainage',
                        'Endocrine': 'Androgens, insulin resistance, IGF-1, cortisol, DHEA-S',
                        'Inflammatory': 'Cytokine pathways, oxidative stress, inflammatory mediators'
                    };
                } else if (conditionLower.includes('scar') || conditionLower.includes('stretch')) {
                    return {
                        'Integumentary': 'Fibroblasts, collagen matrix, elastin fibers, dermal structure',
                        'Circulatory': 'Capillary growth, angiogenesis, tissue perfusion, oxygen delivery',
                        'Endocrine': 'Cortisol levels, stress hormones, growth factors, healing hormones',
                        'Cellular': 'Collagen remodeling, tissue repair, cellular regeneration, wound healing',
                        'Inflammatory': 'Healing inflammation, scar formation, tissue remodeling'
                    };
                } else {
                    return {
                        'Integumentary': 'Skin layers, collagen matrix, elastin fibers, cellular structure',
                        'Circulatory': 'Microcirculation, lymphatic drainage, tissue perfusion',
                        'Metabolic': 'Cellular metabolism, energy production, repair mechanisms',
                        'Endocrine': 'Hormone effects on skin, aging pathways, growth factors',
                        'Inflammatory': 'Oxidative stress, inflammatory aging, tissue damage'
                    };
                }
            }
            
            // Allergen testing protocols
            else if (category === 'allergen') {
                if (conditionLower.includes('food') || conditionLower.includes('milk') || conditionLower.includes('egg') || 
                    conditionLower.includes('peanut') || conditionLower.includes('wheat') || conditionLower.includes('soy')) {
                    return {
                        'Immune System': 'IgE pathways, mast cells, basophils, histamine release, complement cascade',
                        'Digestive': 'GI tract mucosa, intestinal permeability, enzyme systems, microbiome',
                        'Respiratory': 'Airways, bronchi, alveoli, respiratory mucosa, breathing patterns',
                        'Integumentary': 'Skin barriers, dermal layers, sweat glands, hair follicles',
                        'Neurological': 'Vagal responses, autonomic reactions, stress pathways, pain receptors'
                    };
                } else if (conditionLower.includes('pollen') || conditionLower.includes('grass') || conditionLower.includes('tree') || 
                          conditionLower.includes('weed') || conditionLower.includes('ragweed')) {
                    return {
                        'Respiratory': 'Nasal passages, sinuses, bronchi, lung tissue, mucous membranes',
                        'Immune System': 'IgE antibodies, allergic cascade, inflammatory mediators, T-cell responses',
                        'Ocular': 'Conjunctiva, tear ducts, eyelid tissues, corneal surface',
                        'Integumentary': 'Facial skin, exposed skin areas, barrier function',
                        'Neurological': 'Trigeminal nerve, olfactory pathways, autonomic responses'
                    };
                } else if (conditionLower.includes('chemical') || conditionLower.includes('pesticide') || 
                          conditionLower.includes('cleaning') || conditionLower.includes('perfume')) {
                    return {
                        'Detoxification': 'Liver phase I/II, kidney filtration, lymphatic drainage, cellular detox',
                        'Respiratory': 'Airways, alveolar-capillary membrane, respiratory epithelium',
                        'Neurological': 'Blood-brain barrier, neurotransmitter systems, cognitive centers',
                        'Immune System': 'Chemical sensitivity pathways, inflammatory responses, oxidative stress',
                        'Integumentary': 'Skin absorption, barrier function, sebaceous glands, sweat elimination'
                    };
                } else if (conditionLower.includes('drug') || conditionLower.includes('penicillin') || 
                          conditionLower.includes('aspirin') || conditionLower.includes('vaccine')) {
                    return {
                        'Immune System': 'Drug-specific IgE, hapten formation, T-cell mediated responses, anaphylaxis pathways',
                        'Hepatic': 'Drug metabolism, cytochrome P450, conjugation pathways, hepatotoxicity markers',
                        'Renal': 'Drug elimination, nephrotoxicity, filtration capacity, tubular function',
                        'Cardiovascular': 'Drug effects on heart, vascular responses, blood pressure regulation',
                        'Neurological': 'CNS drug effects, neurotoxicity, cognitive impacts, seizure thresholds'
                    };
                } else {
                    return {
                        'Immune System': 'IgE pathways, allergic cascade, mast cell degranulation, histamine release',
                        'Respiratory': 'Airways, bronchi, alveoli, respiratory mucosa, gas exchange',
                        'Integumentary': 'Skin barriers, dermal reactions, urticaria pathways, eczema patterns',
                        'Digestive': 'GI mucosa, intestinal permeability, food processing, microbiome balance',
                        'Neurological': 'Autonomic responses, stress pathways, pain receptors, inflammatory reflexes'
                    };
                }
            }
            
            // Chakra & Aura protocols
            else if (category === 'chakra') {
                return {
                    'Energy Centers': 'Seven main chakras, minor chakras, energy vortexes',
                    'Biofield': 'Aura layers, energy body, etheric double, astral body',
                    'Meridians': 'Energy channels, nadis, acupuncture points, marma points',
                    'Endocrine': 'Chakra-gland connections, hormonal correlations',
                    'Consciousness': 'Spiritual centers, higher self connection, soul alignment'
                };
            }
            
            // Default for other conditions
            else {
                return {
                    'Primary System': 'Main affected organ system and related structures',
                    'Secondary Systems': 'Supporting systems and compensatory mechanisms',
                    'Metabolic': 'Energy pathways and biochemical processes involved',
                    'Immune': 'Inflammatory response and immune system involvement',
                    'Neurological': 'Neural control and nervous system integration'
                };
            }
        }

        // Get scan vs meta information
        function getScanVsMeta(condition, category) {
            const conditionLower = condition.toLowerCase();
            
            if (conditionLower.includes('tinnitus')) {
                return 'Scan + Meta possible (supportive therapy, desensitization)';
            } else if (category === 'allergen') {
                return 'Scan + Vegeto-Test + Desensitization Meta possible';
            } else if (category === 'chakra') {
                return 'Scan + Meta + Imprint possible';
            } else if (category === 'aesthetic') {
                return 'Scan + Meta + Vegeto-Test possible';
            } else if (category === 'pediatric') {
                return 'Scan + Gentle Meta possible (reduced intensity)';
            } else {
                return 'Scan + Meta possible';
            }
        }

        // Get step sequence
        function getStepSequence(condition, category) {
            const conditionLower = condition.toLowerCase();
            
            if (conditionLower.includes('tinnitus')) {
                return [
                    'Calibration → Adjust all',
                    'Test → Absolute model',
                    'Entropy Analysis → Auditory nerve, cochlea, temporal lobe',
                    'Object → Etalon (vascular, nerve, ENT, psycho-emotional)',
                    'Vegeto Test → Remedies (vascular support, antioxidants, calming)',
                    'Meta-Therapy → 7–10 min @ 70–80% (focus: inner ear + brain circulation)',
                    'Comparative Analysis → Pre/Post therapy',
                    'Optional: Repeat scan after ENTROPIA test to monitor resonance'
                ];
            } else if (category === 'aesthetic') {
                if (conditionLower.includes('skin rejuvenation') || conditionLower.includes('anti-aging') || conditionLower.includes('wrinkle')) {
                    return [
                        'Calibration → Adjust all',
                        'Test → Absolute model',
                        'Entropy Analysis → Skin cells, fibroblasts, collagen fibers',
                        'Object → Etalon (collagen, elastin, hyaluronic acid, circulation)',
                        'Vegeto Test → Anti-aging remedies (collagen, antioxidants, phytohormones)',
                        'Meta-Therapy → Face zones + circulation, 10–12 min @ 80–90%',
                        'Comparative Analysis → Pre/Post therapy'
                    ];
                } else if (conditionLower.includes('weight') || conditionLower.includes('cellulite')) {
                    return [
                        'Calibration → Adjust all',
                        'Test → Absolute model',
                        'Entropy Analysis → Fat cells, lymphatics',
                        'Object → Etalon (lipolysis, lymph drainage, detox remedies)',
                        'Vegeto Test → Lipotropic, anti-cellulite remedies (caffeine, green tea, artichoke)',
                        'Meta-Therapy → Abdomen, thighs, lymphatics 12–15 min @ 85%',
                        'Comparative Analysis → Pre/Post therapy'
                    ];
                } else if (conditionLower.includes('hair')) {
                    return [
                        'Calibration → Adjust all',
                        'Test → Absolute model',
                        'Entropy Analysis → Hair follicles, keratinocytes',
                        'Object → Etalon (hair cycle phases, DHT metabolism, vitamins/minerals)',
                        'Vegeto Test → Remedies (saw palmetto, zinc, biotin, B vitamins)',
                        'Meta-Therapy → Scalp circulation, 8–10 min @ 75–85%',
                        'Comparative Analysis → Pre/Post therapy'
                    ];
                } else if (conditionLower.includes('acne') || conditionLower.includes('detox')) {
                    return [
                        'Calibration → Adjust all',
                        'Test → Absolute model',
                        'Entropy Analysis → Sebaceous glands, microbiome',
                        'Object → Etalon (skin flora, hormones, detox pathways)',
                        'Vegeto Test → Remedies (zinc, probiotics, herbal antimicrobials)',
                        'Meta-Therapy → Face zones, 7–10 min @ 70–80%',
                        'Comparative Analysis → Pre/Post therapy'
                    ];
                } else if (conditionLower.includes('scar') || conditionLower.includes('stretch')) {
                    return [
                        'Calibration → Adjust all',
                        'Test → Absolute model',
                        'Entropy Analysis → Scar tissue, fibroblasts',
                        'Object → Etalon (collagen remodeling, angiogenesis, growth factors)',
                        'Vegeto Test → Remedies (vitamin C, centella asiatica, aloe vera)',
                        'Meta-Therapy → Scar/stretch area, 10–12 min @ 85%',
                        'Comparative Analysis → Pre/Post therapy'
                    ];
                } else {
                    const entropyTarget = getEntropyTarget(condition, category);
                    const etalonTarget = getEtalonTarget(condition, category);
                    const metaSettings = getMetaTherapySettings(condition, category);
                    
                    return [
                        'Calibration → Adjust all',
                        'Test → Absolute model',
                        `Entropy Analysis → ${entropyTarget}`,
                        `Object → Etalon ${etalonTarget}`,
                        'Vegeto Test → Remedies',
                        `Meta-Therapy → ${metaSettings}`,
                        'Comparative Analysis → Pre/Post therapy'
                    ];
                }
            } else if (conditionLower.includes('bipolar')) {
                return [
                    'Calibration → Adjust all',
                    'Test → Absolute model (brain regions + endocrine)',
                    'Entropy Analysis → Emotional brain circuits, neurotransmitters',
                    'Object → Etalon (dopamine metabolism, serotonin receptors, cortisol rhythm)',
                    'Vegeto Test → Remedies (mood stabilizers, omega-3, magnesium, adaptogens)',
                    'Meta-Therapy → Brain regions (frontal lobe, limbic), endocrine stabilizers, 8–12 min @ 70–80%',
                    'Comparative Analysis → Pre/Post therapy',
                    'Optional: Repeat aura scan → before & after'
                ];
            } else if (conditionLower.includes('schizophrenia')) {
                return [
                    'Calibration → Adjust all',
                    'Test → Absolute model (brain, immune, endocrine)',
                    'Entropy Analysis → Frontal/temporal lobes, neurotransmitters',
                    'Object → Etalon (dopamine excess, glutamate receptors, immune activation)',
                    'Vegeto Test → Remedies (antioxidants, B vitamins, calming adaptogens)',
                    'Meta-Therapy → 10–15 min @ 70–80% → frontal cortex + limbic stability',
                    'Comparative Analysis → Pre/Post therapy',
                    'Optional: Imprint → calming frequencies into water'
                ];
            } else if (conditionLower.includes('dissociative') || conditionLower.includes('multiple personality')) {
                return [
                    'Calibration → Adjust all',
                    'Test → Absolute model (brain + psycho field)',
                    'Entropy Analysis → Trauma circuits, memory pathways',
                    'Object → Etalon (PTSD markers, cortisol, dissociative states)',
                    'Vegeto Test → Remedies (trauma healing, emotional stabilizers, adaptogens)',
                    'Meta-Therapy → Limbic + prefrontal integration, 8–10 min @ 70%',
                    'Comparative Analysis → Pre/Post therapy',
                    'Optional → Aura balancing, chakra alignment'
                ];
            } else {
                const entropyTarget = getEntropyTarget(condition, category);
                const etalonTarget = getEtalonTarget(condition, category);
                const metaSettings = getMetaTherapySettings(condition, category);
                
                return [
                    'Calibration → Adjust all',
                    'Test → Absolute model',
                    `Entropy Analysis → ${entropyTarget}`,
                    `Object → Etalon ${etalonTarget}`,
                    'Vegeto Test → Remedies',
                    `Meta-Therapy → ${metaSettings}`,
                    'Comparative Analysis → Pre/Post therapy'
                ];
            }
        }

        // Get entropy analysis target
        function getEntropyTarget(condition, category) {
            const conditionLower = condition.toLowerCase();
            
            if (conditionLower.includes('tinnitus')) {
                return 'Auditory nerve, cochlea, temporal lobe';
            } else if (category === 'cardiovascular') {
                return 'Healthy myocardium → ischemia/damage grades';
            } else if (category === 'respiratory') {
                return 'Healthy alveoli → inflammation/fibrosis grades';
            } else if (category === 'digestive') {
                return 'Healthy mucosa → inflammation/ulceration grades';
            } else if (category === 'neurology') {
                return 'Healthy neurons → degeneration/damage grades';
            } else if (category === 'endocrine') {
                return 'Healthy glandular tissue → dysfunction grades';
            } else if (category === 'renal') {
                return 'Healthy nephrons → damage/fibrosis grades';
            } else if (category === 'musculoskeletal') {
                return 'Healthy bone/cartilage → degeneration grades';
            } else if (category === 'dermatology') {
                return 'Healthy skin layers → pathology grades';
            } else if (category === 'aesthetic') {
                return 'Healthy skin matrix → aging/damage grades';
            } else if (category === 'allergen') {
                return 'Normal immune response → allergic reaction grades';
            } else if (category === 'chakra') {
                return 'Balanced chakras → energy blockage grades';
            } else {
                return 'Healthy tissue → pathology grades';
            }
        }

        // Get etalon target
        function getEtalonTarget(condition, category) {
            const conditionLower = condition.toLowerCase();
            
            if (conditionLower.includes('tinnitus')) {
                return '(vascular, nerve, ENT, psycho-emotional)';
            } else if (category === 'cardiovascular') {
                return '(heart, vessels, circulation)';
            } else if (category === 'respiratory') {
                return '(lungs, airways, oxygenation)';
            } else if (category === 'digestive') {
                return '(GI tract, liver, pancreas)';
            } else if (category === 'neurology') {
                return '(brain, nerves, neurotransmitters)';
            } else if (category === 'endocrine') {
                return '(glands, hormones, metabolism)';
            } else if (category === 'renal') {
                return '(kidneys, urinary system)';
            } else if (category === 'musculoskeletal') {
                return '(bones, joints, muscles)';
            } else if (category === 'dermatology') {
                return '(skin, hair, nails)';
            } else if (category === 'aesthetic') {
                return '(collagen, elastin, cellular matrix)';
            } else if (category === 'allergen') {
                return '(allergens, immune system, detoxification)';
            } else if (category === 'chakra') {
                return '(chakras, aura, energy centers)';
            } else {
                return '(related organ systems)';
            }
        }

        // Get meta-therapy settings
        function getMetaTherapySettings(condition, category) {
            const conditionLower = condition.toLowerCase();
            
            if (conditionLower.includes('tinnitus')) {
                return '7–10 min @ 70–80% (focus: inner ear + brain circulation)';
            } else if (category === 'pediatric') {
                return '3–5 min @ 50–60% (gentle intensity)';
            } else if (category === 'aesthetic') {
                return '5–7 min @ 60–70% (tissue regeneration)';
            } else if (category === 'allergen') {
                return '3–5 min @ 40–60% (desensitization therapy)';
            } else if (category === 'chakra') {
                return '3–5 min per chakra @ 50–70% (energy balancing)';
            } else if (conditionLower.includes('acute') || conditionLower.includes('severe')) {
                return '7–10 min @ 80–90% (intensive therapy)';
            } else if (conditionLower.includes('chronic')) {
                return '10–15 min @ 60–70% (sustained therapy)';
            } else {
                return '5–7 min @ 70–80% (standard therapy)';
            }
        }

        // Get etalon groups
        function getEtalonGroups(condition, category) {
            const conditionLower = condition.toLowerCase();
            
            if (conditionLower.includes('tinnitus')) {
                return {
                    'Organs/Tissues': 'Cochlea, Vestibular apparatus, Auditory cortex, Carotids',
                    'Pathomorphology': 'Neuroinflammation, Hearing loss, Ototoxic damage',
                    'Microorganisms': 'Viral labyrinthitis, CMV, HSV, Lyme (neuro-borrelia)',
                    'Biochemical': 'Circulation, Oxidative stress, Mitochondrial dysfunction',
                    'Remedies': 'Ginkgo biloba, Magnesium, Vitamin B complex, Stress remedies',
                    'Psychological': 'Insomnia, Anxiety, Depression-related patterns'
                };
            } else {
                return getStandardEtalonGroups(condition, category);
            }
        }

        // Get standard etalon groups for other conditions
        function getStandardEtalonGroups(condition, category) {
            // This would contain the detailed etalon groups for each category
            // For brevity, returning a simplified version
            return {
                'Organs/Tissues': 'Primary affected organs and tissues',
                'Pathomorphology': 'Disease-specific pathological changes',
                'Microorganisms': 'Associated pathogens and microorganisms',
                'Biochemical': 'Relevant biochemical markers and pathways',
                'Remedies': 'Therapeutic agents and natural remedies',
                'Additional': 'Category-specific additional etalons'
            };
        }

        // Get priority etalons
        function getPriorityEtalons(condition, category) {
            const conditionLower = condition.toLowerCase();
            
            if (conditionLower.includes('tinnitus')) {
                return [
                    'Cochlear hair cells',
                    'Auditory nerve myelin',
                    'Brainstem auditory pathway',
                    'Microcirculation profile',
                    'Stress and anxiety resonance fields'
                ];
            } else if (category === 'aesthetic') {
                if (conditionLower.includes('skin rejuvenation') || conditionLower.includes('anti-aging') || conditionLower.includes('wrinkle')) {
                    return [
                        'Collagen I & III',
                        'Fibroblasts',
                        'Hyaluronic acid',
                        'Mitochondria (ATP)',
                        'Antioxidant systems'
                    ];
                } else if (conditionLower.includes('weight') || conditionLower.includes('cellulite')) {
                    return [
                        'Adipocytes',
                        'Lipid metabolism',
                        'Lymphatic vessels',
                        'Circulatory flow',
                        'Lipolysis enzymes'
                    ];
                } else if (conditionLower.includes('hair')) {
                    return [
                        'Hair follicle cycle',
                        'DHT metabolism',
                        'Keratin production',
                        'Scalp microcirculation',
                        'Follicle stem cells'
                    ];
                } else if (conditionLower.includes('acne') || conditionLower.includes('detox')) {
                    return [
                        'Sebaceous glands',
                        'Skin flora balance',
                        'Inflammatory markers',
                        'Insulin resistance',
                        'Detox pathways'
                    ];
                } else if (conditionLower.includes('scar') || conditionLower.includes('stretch')) {
                    return [
                        'Collagen cross-linking',
                        'Fibroblast activity',
                        'Angiogenesis factors',
                        'Growth factors',
                        'Tissue remodeling'
                    ];
                } else {
                    return getStandardPriorityEtalons(condition, category);
                }
            } else if (conditionLower.includes('bipolar')) {
                return [
                    'Dopamine receptors',
                    'Thyroid hormones',
                    'Cortisol circadian rhythm',
                    'Mitochondrial function',
                    'Serotonin balance'
                ];
            } else if (conditionLower.includes('schizophrenia')) {
                return [
                    'Dopamine/glutamate metabolism',
                    'Microglial inflammation',
                    'Temporal lobe circuits',
                    'Frontal cortex function',
                    'Neurotransmitter balance'
                ];
            } else if (conditionLower.includes('dissociative') || conditionLower.includes('multiple personality')) {
                return [
                    'Amygdala reactivity',
                    'Cortisol stress markers',
                    'Trauma resonance fields',
                    'Memory integration circuits',
                    'Prefrontal-limbic connectivity'
                ];
            } else {
                return getStandardPriorityEtalons(condition, category);
            }
        }

        // Get standard priority etalons
        function getStandardPriorityEtalons(condition, category) {
            // Simplified version - would be expanded for each condition
            return [
                'Primary pathology markers',
                'Inflammatory response',
                'Tissue damage indicators',
                'Functional capacity',
                'Recovery potential'
            ];
        }

        // Get clinical notes
        function getClinicalNotes(condition, category) {
            const conditionLower = condition.toLowerCase();
            
            if (conditionLower.includes('tinnitus')) {
                return [
                    'Always compare left vs right ear structures',
                    'Look for compensatory vs degenerative signals in auditory pathways',
                    'Meta-therapy is supportive: improves circulation, reduces neuroinflammation, and calms stress circuits',
                    'Combine with lifestyle (reduce caffeine, noise exposure, stress)'
                ];
            } else if (category === 'aesthetic') {
                if (conditionLower.includes('skin rejuvenation') || conditionLower.includes('anti-aging') || conditionLower.includes('wrinkle')) {
                    return [
                        'Combine with hydration, antioxidants, collagen peptides',
                        'Check for E < 0.425 on Entropy',
                        'Focus meta-therapy on facial zones and circulation',
                        'Monitor skin elasticity and hydration levels'
                    ];
                } else if (conditionLower.includes('weight') || conditionLower.includes('cellulite')) {
                    return [
                        'Enhance with exercise + detox protocols',
                        'Check for E < 0.425 on Entropy',
                        'Focus on lymphatic drainage and circulation',
                        'Monitor body composition changes'
                    ];
                } else if (conditionLower.includes('hair')) {
                    return [
                        'Check stress markers and detox burden (liver/kidneys)',
                        'Monitor DHT levels and hormonal balance',
                        'Focus meta-therapy on scalp circulation',
                        'Combine with nutritional support (zinc, biotin, B vitamins)'
                    ];
                } else if (conditionLower.includes('acne') || conditionLower.includes('detox')) {
                    return [
                        'Combine with gut healing and low-glycemic diet',
                        'Check for E < 0.425 on Entropy',
                        'Focus on microbiome balance and detox pathways',
                        'Monitor hormonal factors (androgens, insulin)',
                        'Address stress and sleep quality'
                    ];
                } else if (conditionLower.includes('scar') || conditionLower.includes('stretch')) {
                    return [
                        'Useful post-surgery or for cosmetic scar reduction',
                        'Check for E < 0.425 on Entropy',
                        'Focus meta-therapy on affected tissue areas',
                        'Monitor collagen remodeling progress',
                        'Combine with topical treatments for enhanced results'
                    ];
                } else {
                    return getStandardClinicalNotes(condition, category);
                }
            } else if (conditionLower.includes('bipolar')) {
                return [
                    'Always test neurotransmitters + hormones (dopamine, serotonin, cortisol, thyroid)',
                    'Check toxins, drugs, heavy metals that may aggravate symptoms',
                    'Aura/Chakra scans give extra insight (imbalances often map to third eye, solar plexus)',
                    'Meta-therapy is supportive: stabilizes brain frequency fields, improves neurotransmitter balance',
                    'Combine with clinical psychiatric treatment — Bioplasm is complementary, not a replacement',
                    'Monitor mood cycles and energy patterns'
                ];
            } else if (conditionLower.includes('schizophrenia')) {
                return [
                    'Always test neurotransmitters + hormones (dopamine, serotonin, cortisol, thyroid)',
                    'Check for viral/bacterial triggers and immune activation',
                    'Aura/Chakra scans show fragmentation patterns (crown, third eye common)',
                    'Meta-therapy stabilizes brain frequency fields, reduces neuroinflammation',
                    'Combine with clinical psychiatric treatment — Bioplasm is complementary, not a replacement',
                    'Monitor cognitive function and reality testing'
                ];
            } else if (conditionLower.includes('dissociative') || conditionLower.includes('multiple personality')) {
                return [
                    'Always assess trauma patterns and stress axis function',
                    'Check cortisol, norepinephrine, and PTSD markers',
                    'Aura/Chakra scans reveal identity fragmentation (root, solar plexus, crown)',
                    'Meta-therapy supports limbic-prefrontal integration and trauma healing',
                    'Combine with trauma-informed psychiatric treatment — Bioplasm is complementary',
                    'Monitor dissociative episodes and integration progress'
                ];
            } else {
                return getStandardClinicalNotes(condition, category);
            }
        }

        // Get standard clinical notes
        function getStandardClinicalNotes(condition, category) {
            let notes = ['Check for E < 0.425 on Entropy'];
            
            if (category === 'pediatric') {
                notes.push('Use gentle intensity settings');
                notes.push('Parent/guardian must be present');
            } else if (category === 'cardiovascular') {
                notes.push('Monitor blood pressure and pulse');
            } else if (category === 'respiratory') {
                notes.push('Monitor oxygen saturation');
            }
            
            notes.push('Document all findings and responses');
            return notes;
        }

        // Categorize condition
        function categorizeCondition(condition) {
            for (let [category, pattern] of categoryRules) {
                if (pattern.test(condition)) {
                    return category;
                }
            }
            return "other";
        }

        // Generate protocol for each condition
        function generateProtocol(condition) {
            const category = categorizeCondition(condition);
            const systemsToScan = getDetailedSystemsToScan(condition, category);
            const scanVsMeta = getScanVsMeta(condition, category);
            const stepSequence = getStepSequence(condition, category);
            const etalonGroups = getEtalonGroups(condition, category);
            const priorityEtalons = getPriorityEtalons(condition, category);
            const clinicalNotes = getClinicalNotes(condition, category);
            
            return {
                condition: condition,
                category: category,
                systemsToScan: systemsToScan,
                scanVsMeta: scanVsMeta,
                stepSequence: stepSequence,
                etalonGroups: etalonGroups,
                priorityEtalons: priorityEtalons,
                clinicalNotes: clinicalNotes
            };
        }

        // Initialize protocols
        function initializeProtocols() {
            allProtocols = medicalConditions.map(condition => generateProtocol(condition));
            displayProtocols(allProtocols);
            updateResultCount(allProtocols.length);
        }

        // Display protocols
        function displayProtocols(protocols) {
            const protocolGrid = document.getElementById('protocolGrid');
            const noResults = document.getElementById('noResults');
            
            if (protocols.length === 0) {
                protocolGrid.innerHTML = '';
                noResults.classList.remove('hidden');
                return;
            }
            
            noResults.classList.add('hidden');
            
            protocolGrid.innerHTML = protocols.map((protocol, index) => `
                <div class="protocol-card ${protocol.category} p-4 rounded-lg cursor-pointer fade-in" 
                     style="animation-delay: ${(index % 20) * 0.05}s"
                     onclick="showProtocolDetails('${protocol.condition.replace(/'/g, "\\'")}')">
                    <div class="flex justify-between items-start mb-3">
                        <h4 class="font-semibold text-gray-800 text-sm leading-tight">${protocol.condition}</h4>
                        <span class="text-xs text-gray-500 ml-2">${getCategoryIcon(protocol.category)}</span>
                    </div>
                    
                    <div class="space-y-2 mb-3">
                        <div class="text-xs bg-blue-100 text-blue-800 px-2 py-1 rounded">
                            ${Object.keys(protocol.systemsToScan).length} Systems to Scan
                        </div>
                        <div class="text-xs bg-green-100 text-green-800 px-2 py-1 rounded">
                            ${protocol.scanVsMeta}
                        </div>
                        <div class="text-xs bg-purple-100 text-purple-800 px-2 py-1 rounded">
                            ${protocol.priorityEtalons.length} Priority Etalons
                        </div>
                    </div>
                    
                    <div class="text-xs text-gray-600 line-clamp-2">
                        Systems: ${Object.keys(protocol.systemsToScan).slice(0, 2).join(', ')}...
                    </div>
                </div>
            `).join('');
        }

        // Show protocol details
        function showProtocolDetails(conditionName) {
            const protocol = allProtocols.find(p => p.condition === conditionName);
            if (!protocol) return;
            
            const modal = document.getElementById('protocolModal');
            const modalTitle = document.getElementById('modalTitle');
            const modalContent = document.getElementById('modalContent');
            
            modalTitle.textContent = protocol.condition;
            
            modalContent.innerHTML = `
                <!-- Disease Header -->
                <div class="mb-6 bg-gradient-to-r from-blue-600 to-purple-600 text-white rounded-lg p-4">
                    <h2 class="text-xl font-bold"># Disease: ${protocol.condition}</h2>
                </div>

                <!-- Systems to Scan -->
                <div class="mb-6 bg-blue-50 rounded-lg p-4 border border-blue-200">
                    <h3 class="text-lg font-semibold text-blue-800 mb-3">## Systems to Scan:</h3>
                    <div class="space-y-3 text-sm text-blue-700">
                        ${Object.entries(protocol.systemsToScan).map(([system, details]) => 
                            `<div><strong>${system}:</strong> ${details}</div>`
                        ).join('')}
                    </div>
                </div>

                <!-- Scan vs Meta -->
                <div class="mb-6 bg-green-50 rounded-lg p-4 border border-green-200">
                    <h3 class="text-lg font-semibold text-green-800 mb-3">## Scan vs Meta:</h3>
                    <div class="text-sm text-green-700">
                        <span class="flex items-center"><span class="mr-2">-</span>${protocol.scanVsMeta}</span>
                    </div>
                </div>

                <!-- Step Sequence -->
                <div class="mb-6 bg-purple-50 rounded-lg p-4 border border-purple-200">
                    <h3 class="text-lg font-semibold text-purple-800 mb-3">## Step Sequence (Buttons):</h3>
                    <ol class="space-y-2 text-sm text-purple-700">
                        ${protocol.stepSequence.map((step, index) => 
                            `<li class="flex items-start">
                                <span class="font-medium mr-2">${index + 1}.</span>
                                <span>${step}</span>
                            </li>`
                        ).join('')}
                    </ol>
                </div>

                <!-- Etalon Groups -->
                <div class="mb-6 bg-orange-50 rounded-lg p-4 border border-orange-200">
                    <h3 class="text-lg font-semibold text-orange-800 mb-3">## Etalon Groups:</h3>
                    <div class="space-y-3 text-sm text-orange-700">
                        ${Object.entries(protocol.etalonGroups).map(([group, details]) => 
                            `<div><strong>${group}:</strong> ${details}</div>`
                        ).join('')}
                    </div>
                </div>

                <!-- Priority Etalons -->
                <div class="mb-6 bg-red-50 rounded-lg p-4 border border-red-200">
                    <h3 class="text-lg font-semibold text-red-800 mb-3">## Priority Etalons:</h3>
                    <ul class="space-y-1 text-sm text-red-700">
                        ${protocol.priorityEtalons.map(etalon => 
                            `<li class="flex items-center"><span class="mr-2">-</span>${etalon}</li>`
                        ).join('')}
                    </ul>
                </div>

                <!-- Notes -->
                <div class="mb-6 bg-yellow-50 rounded-lg p-4 border border-yellow-200">
                    <h3 class="text-lg font-semibold text-yellow-800 mb-3">## Notes:</h3>
                    <ul class="space-y-1 text-sm text-yellow-700">
                        ${protocol.clinicalNotes.map(note => 
                            `<li class="flex items-start"><span class="mr-2">-</span>${note}</li>`
                        ).join('')}
                    </ul>
                </div>
                
                <div class="mt-6 flex justify-center">
                    <button onclick="closeModal();" 
                            class="bg-blue-600 hover:bg-blue-700 text-white px-8 py-3 rounded-lg font-medium transition-colors">
                        Close Protocol
                    </button>
                </div>
            `;
            
            modal.classList.remove('hidden');
        }

        // Get category icon
        function getCategoryIcon(category) {
            const icons = {
                cardiovascular: '❤️',
                respiratory: '🫁',
                digestive: '🍽️',
                neurology: '🧠',
                endocrine: '⚡',
                renal: '🔵',
                musculoskeletal: '🦴',
                dermatology: '🌸',
                reproductive: '👥',
                hematology: '🩸',
                infectious: '🦠',
                ophthalmology: '👁️',
                pediatric: '👶',
                aesthetic: '✨',
                allergen: '🌾',
                chakra: '🕉️',
                other: '📋'
            };
            return icons[category] || '📋';
        }

        // Search functionality
        function searchProtocols() {
            const searchTerm = document.getElementById('searchInput').value.toLowerCase();
            let filteredProtocols = allProtocols;
            
            if (searchTerm) {
                filteredProtocols = allProtocols.filter(protocol => 
                    protocol.condition.toLowerCase().includes(searchTerm)
                );
            }
            
            if (currentFilter !== 'all') {
                filteredProtocols = filteredProtocols.filter(protocol => 
                    protocol.category === currentFilter
                );
            }
            
            displayProtocols(filteredProtocols);
            updateResultCount(filteredProtocols.length);
        }

        // Filter by category
        function filterByCategory(category) {
            currentFilter = category;
            
            // Update active filter button
            document.querySelectorAll('.category-filter').forEach(btn => {
                btn.classList.remove('active');
            });
            event.target.classList.add('active');
            
            searchProtocols();
        }

        // Close modal
        function closeModal() {
            document.getElementById('protocolModal').classList.add('hidden');
        }

        // Update result count
        function updateResultCount(count) {
            document.getElementById('resultCount').textContent = count;
        }

        // Initialize the application
        document.addEventListener('DOMContentLoaded', function() {
            initializeProtocols();
            
            // Add enter key support for search
            document.getElementById('searchInput').addEventListener('keypress', function(e) {
                if (e.key === 'Enter') {
                    searchProtocols();
                }
            });
            
            // Close modal when clicking outside
            document.getElementById('protocolModal').addEventListener('click', function(e) {
                if (e.target === this) {
                    closeModal();
                }
            });
            
            console.log(`NLS Protocol Database initialized with ${medicalConditions.length} protocols`);
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'97199d8483030f09',t:'MTc1NTYwNjEzNC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
