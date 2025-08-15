# 🤖 EpiMind AI - IAAM Predictor Enhanced

Asistent AI avansat pentru evaluarea riscului de infecții asociate asistenței medicale (IAAM), dezvoltat pentru UMF "Grigore T. Popa" Iași.

## ✨ Funcționalități Principale

### 🧠 AI Conversational Inteligent
- **Chat natural în română** pentru introducerea datelor medicale
- **Fallback inteligent** când Ollama nu este disponibil
- **Extracție automată** de date din text natural
- **Validare în timp real** a informațiilor medicale

### 🎯 Predicție IAAM Avansată
- **Algoritm îmbunătățit** cu scoring progresiv
- **Evaluare completă** SOFA și qSOFA
- **Analiza dispozitivelor invazive** cu durata de utilizare
- **Interpretare microbiologie** cu rezistențe multiple
- **Markeri inflamatori** (CRP, PCT, leucocite)

### 📊 Interfață Modernă
- **Design responsiv** cu tema întunecată
- **Grafice interactive** pentru distribuția scorului
- **Istoric pacienți** persistent
- **Export date** în format JSON
- **Sidebar informativ** cu ghiduri

### 🔧 Funcționalități Tehnice
- **Validare robustă** a datelor medicale
- **Gestionare erori** completă
- **Logging** pentru debugging
- **Testare automată** cu suite complete
- **Generator date demo** pentru testare

## 🚀 Instalare și Configurare

### Cerințe Sistem
- Python 3.8+
- 4GB RAM minim
- Conexiune internet pentru AI (opțional)

### Instalare Rapidă
\`\`\`bash
# Clonează repository-ul
git clone <repository-url>
cd epimind-ai

# Instalează dependențele
pip install -r requirements.txt

# Rulează aplicația
streamlit run scripts/epimind_ai_enhanced.py
\`\`\`

### Configurare AI (Opțional)
Pentru funcționalitate AI completă:
\`\`\`bash
# Instalează Ollama
curl -fsSL https://ollama.ai/install.sh | sh

# Descarcă modelul
ollama pull llama3.2:3b

# Pornește Ollama
ollama serve
\`\`\`

**Notă:** Aplicația funcționează perfect și fără Ollama, folosind răspunsuri inteligente pre-programate.

## 📖 Ghid de Utilizare

### 1. Introducerea Datelor
Vorbește natural cu AI-ul în română:

\`\`\`
"Pacientul este internat de 5 zile, are cateter central de 3 zile și ventilație mecanică"
"Leucocite 15.000, CRP 120, procalcitonină 2.5, temperatură 38.5°C"
"Cultură pozitivă E.coli ESBL+, Glasgow 12, TA 90/60"
\`\`\`

### 2. Date Necesare pentru IAAM
- ⏰ **Timp spitalizare** (≥48h obligatoriu)
- 🔧 **Dispozitive invazive** și durata
- 🧪 **Analize laborator** (WBC, CRP, PCT)
- 🦠 **Culturi microbiologice** și rezistențe
- 💓 **Parametri vitali** (TA, FC, T°, FR)
- 🧠 **Scor Glasgow** și status neurologic

### 3. Interpretarea Rezultatelor
- 🟢 **SCĂZUT** (0-49): Monitorizare standard
- 🟡 **MODERAT** (50-79): Supraveghere extinsă  
- 🟠 **ÎNALT** (80-109): Măsuri preventive
- 🔴 **FOARTE ÎNALT** (110-139): Consult urgent
- 🚨 **CRITIC** (≥140): Alertă IAAM

## 🧪 Testare și Validare

### Rulează Testele
\`\`\`bash
# Test complet al funcționalităților
python scripts/test_epimind.py

# Generează date demo
python scripts/demo_data_generator.py
\`\`\`

### Scenarii de Test Incluse
- ✅ Pacienți cu risc scăzut/moderat/înalt/critic
- ✅ Extracție date din text natural
- ✅ Calcule SOFA/qSOFA
- ✅ Microbiologie cu rezistențe
- ✅ Workflow complet de evaluare

## 🏥 Algoritm Medical

### Scoring IAAM
1. **Criteriu temporal**: ≥48h spitalizare (obligatoriu)
2. **Dispozitive invazive**: Scoring progresiv pe durata
3. **Microbiologie**: Bacterii + rezistențe multiple
4. **Severitate clinică**: SOFA + qSOFA
5. **Inflamație**: CRP, PCT, leucocite
6. **Factori risc**: Febră, hipotensiune, disfuncții organe

### Bacterii și Rezistențe Suportate
- **Bacterii**: E.coli, Klebsiella, Pseudomonas, Acinetobacter, S.aureus, etc.
- **Rezistențe**: ESBL, MRSA, VRE, CRE, KPC, NDM, XDR, PDR

## 🔧 Arhitectura Tehnică

### Componente Principale
- **PatientData**: Structură de date validată
- **EnhancedOllamaAI**: Client AI cu fallback
- **EnhancedIAAMPredictor**: Motor de predicție
- **EnhancedMedicalDataExtractor**: Extractor NLP
- **EnhancedChatInterface**: Interfață conversațională

### Funcționalități Avansate
- **Validare automată** a valorilor medicale
- **Conversie unități** (zile→ore, /μL→x10³/μL)
- **Detectare pattern** pentru dispozitive și bacterii
- **Scoring adaptiv** bazat pe severitate
- **Persistență date** în session state

## 📊 Exemple de Utilizare

### Caz Clinic 1: Risc Moderat
\`\`\`
Input: "Pacient internat de 4 zile, CVC de 3 zile, leucocite 12000, CRP 80"
Output: Risc MODERAT (65 puncte) - Supraveghere extinsă
\`\`\`

### Caz Clinic 2: Risc Critic  
\`\`\`
Input: "10 zile internare, ventilație 8 zile, CVC 10 zile, PCT 12, E.coli XDR+"
Output: Risc CRITIC (180 puncte) - Alertă IAAM imediată
\`\`\`

## 🤝 Contribuții și Dezvoltare

### Structura Proiectului
\`\`\`
epimind-ai/
├── scripts/
│   ├── epimind_ai_enhanced.py    # Aplicația principală
│   ├── test_epimind.py           # Suite de teste
│   └── demo_data_generator.py    # Generator date demo
├── requirements.txt              # Dependențe Python
└── README.md                     # Documentația
\`\`\`

### Dezvoltare Viitoare
- [ ] Integrare cu sisteme spitalicești (HL7/FHIR)
- [ ] Machine learning pentru predicții îmbunătățite
- [ ] API REST pentru integrări externe
- [ ] Dashboard pentru epidemiologi
- [ ] Raportare automată CPIAAM

## 📄 Licență și Contact

**Dezvoltat pentru:** UMF "Grigore T. Popa" Iași  
**Versiune:** 4.0.0 Enhanced  
**Status:** Complet funcțional și testat  

Pentru suport tehnic sau întrebări medicale, contactați echipa de dezvoltare.

---

*🤖 EpiMind AI - Inteligența artificială în serviciul siguranței pacientului*
