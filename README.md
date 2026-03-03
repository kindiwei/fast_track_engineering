# 🚀 Azure Blob JSON Processor

Python Project:

- 🔐 Authentication with Service Principal (Azure AD)
- ☁️ Reading files in Azure Blob Storage
- 📄 Processamento de nested JSON
- 📊 Lists normalization (`issues`, `assignee`, `'timestamps'`)
- 🔒 Safety uses of enviroment variables with `.env`

---

## 🛠️ Technologies used

- Python 3.10+
- Medallion Architecture
- functions
- azure-identity
- azure-storage-blob
- pandas
- python-dotenv
- requests (`to get info from API`)
- lambda functions

---

## 📂 Scruture of Project
project-root/
│
├── data/
│ ├── bronze/
│ │ └──db_bronze.parquet
│ ├── silver/
│ │ └──db_silver.parquet
│ └── gold/
│   └──db_gold.parquet
│
├── src/
│ ├── bronze/
│ │ └── nb_ingest_json.ipynb
│ ├── silver/
│ │ └── nb_transform_json_silver.ipynb
│ ├── gold/
│ │ └── nb_transform_gold.ipynb
│ ├── functions/
│ │ └── nb_function_read_db.ipynb
│ │ └── nb_function_sla_calculation_holidays.ipynb
│ │ └── nb_function_write_db.ipynb
│ └── sla_calculation.ipynb
│
├── .env
├── .gitignore
├── requirements.txt
└── README.md

---

## 🔐 Configurations of Enviroments Variables

Create a file `.env` in root of project:
AZURE_TENANT_ID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
AZURE_CLIENT_ID=xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
AZURE_CLIENT_SECRET=seu_secret_aqui
ACCOUNT_URL=https://sua-conta.blob.core.windows.net


⚠️ Never send the `.env` to GitHub.

Add in `.gitignore`:
.env

---

## 📦 Instalation

▶️ Clone the repository:

```bash
git clone https://github.com/seu-usuario/seu-repo.git
cd seu-repo

▶️ Create a virtuam enviroment:
python -m venv .venv
source .venv/bin/activate  # Linux / WSL
# or
.venv\Scripts\activate  # Windows

▶️ Install all dependencies:
pip install -r requirements.txt

▶️ Execution
python src/bronze/nb_ingest_json.ipynb
python src/silver/nb_transform_json_silver.ipynb
python src/gold/nb_transform_gold.ipynb

☁️ Projeto Flow

1. Anthenticate in Azure with Service Principal
2. Conect to a Blob Storage
3. Read JSON file
4. Normalize nested structures
5. Convert in DataFrame

🔒 Security

- .env uses
- Service Principal
- Non versionated Secrets

📌 Future improvements

- Upload of data processed to Data Lake
- Databricks Integration
- Deploy with Azure Function
- Automated Tests

👤 Author

Kindi Zhuo Ming Wei
Data Engineering | Azure | Databricks | Python

⭐ Contrubution

Contributions are welcome. Please feel free to submit a pull request!