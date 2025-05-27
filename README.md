# Natural Language Database Query Interface

A web-based application that allows users to query their AWS PostgreSQL databases using natural language questions. Powered by OpenAI's GPT models, this tool converts plain English questions into SQL queries and displays results in an interactive interface.

## 🚀 Features

- **Natural Language Processing**: Ask questions in plain English
- **AI-Powered SQL Generation**: Automatic conversion to PostgreSQL queries using OpenAI GPT
- **Real-Time Results**: Interactive data table display
- **Error Handling**: Clear error messages and debugging information
- **Schema Discovery**: Automatic detection and display of database columns
- **User-Friendly Interface**: Clean web interface built with Gradio

## 📋 Prerequisites

Before running this application, ensure you have:

- **AWS RDS PostgreSQL Database**: Already deployed and accessible
- **OpenAI API Key**: Valid API key for GPT model access
- **Python 3.8+**: Python environment setup
- **Database Credentials**: Connection details for your PostgreSQL database

## 🛠️ Installation

1. **Clone the repository**
   ```bash
   git https://github.com/TingAnWang/Natural-Language-SQL-Query-Interface.git
   ```
2. **Install required packages**

3. **Set up environment variables** (Optional)
   ```bash
   export OPENAI_API_KEY="your-openai-api-key"
   export PG_HOST="your-database-host"
   export PG_USER="your-username"
   export PG_PWD="your-password"
   export PG_DB="your-database-name"
   ```

## 📦 Dependencies

```
gradio>=4.0.0
openai>=1.0.0
pandas>=1.5.0
sqlalchemy>=2.0.0
psycopg2-binary>=2.9.0
```

## ⚙️ Configuration

Update the database configuration in the main script:

```python
# Database Configuration
PG_USER = "your_username"
PG_PWD = "your_password"
PG_HOST = "your-rds-endpoint.region.rds.amazonaws.com"
PG_PORT = 5432
PG_DB = "your_database_name"

# OpenAI Configuration
openai_api_key = "your-openai-api-key"
```

## 🏗️ Architecture

```
┌─────────────────┐    ┌──────────────┐    ┌─────────────────┐
│   Gradio UI     │────│  OpenAI GPT  │────│  PostgreSQL     │
│  (Frontend)     │    │ (AI Service) │    │ (AWS RDS)       │
└─────────────────┘    └──────────────┘    └─────────────────┘
```

## 🔒 Security Notes

- **Never commit API keys** to version control
- **Use environment variables** for sensitive configuration
- **Ensure proper AWS security groups** allow database access
- **Consider VPC configuration** for enhanced security
- **Regular credential rotation** is recommended

## 🐛 Troubleshooting

### Common Issues

**Connection Error**
- Verify AWS RDS endpoint and credentials
- Check security groups allow inbound connections
- Ensure database is publicly accessible (if needed)

**OpenAI API Error**
- Verify API key is valid and has sufficient credits
- Check model name (use "gpt-4o" or "gpt-4.1")

**Query Generation Issues**
- Ensure table and column names are accurate
- Try more specific questions
- Check database schema matches expectations

## 📊 AWS RDS Setup Requirements

Your PostgreSQL database should have:

- **Public accessibility** enabled (or proper VPC configuration)
- **Security group** allowing inbound connections on port 5432
- **Database user** with appropriate SELECT permissions
- **SSL/TLS** configuration (recommended)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
