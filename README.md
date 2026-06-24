# 📸 Rede Social Flesh

Uma aplicação web estruturada como uma rede social focada no compartilhamento de fotos, desenvolvida em Python com o ecossistema Flask. O projeto conta com autenticação de usuários, criação de perfis personalizáveis e um feed dinâmico de postagens.

---

## 🛠️ Tecnologias Utilizadas

* **Back-end:** Python, Flask
* **Formulários e Validação:** Flask-WTF / WTForms
* **Banco de Dados & ORM:** SQLite, SQLAlchemy (gerenciado via `create_database.py`)
* **Front-end:** HTML5, Bootstrap 5, Jinja2 

---

## 🚀 Principais Funcionalidades

* **Autenticação Segura:** Criação de conta (`createaccount.html`) e login de usuários com validação de dados via WTForms integrados ao Bootstrap.
* **Feed Dinâmico:** Visualização cronológica das fotos publicadas pelos usuários na plataforma (`feed.html`).
* **Perfis Personalizáveis:** Página dedicada de perfil (`profile.html`) onde são exibidas as informações e as fotos publicadas pelo respectivo usuário.
* **Upload de Imagens:** Upload e armazenamento local das fotos publicadas (`static/posts_photos`).

---

## 🗄️ Modelo de Dados (Banco de Dados)

A aplicação utiliza o **SQLite** e o ORM **SQLAlchemy** para gerenciar as entidades do sistema através de um relacionamento **1:N** (Um para Muitos):

* **User (Usuário):** Armazena as informações cadastrais (id, username, email, password_hash, profile_photo).
* **Post (Postagem):** Armazena os dados das fotos publicadas (id, image_path, creation_date, user_id). 
  * *Relacionamento:* Cada postagem está vinculada a um único usuário através da Foreign Key (`user_id`).

---

## 📂 Estrutura do Projeto

O projeto segue a estrutura padrão de pacotes recomendada para o desenvolvimento com Flask:

* `app.py`: Ponto de entrada para execução do servidor Flask.
* `create_database.py`: Script responsável por inicializar e estruturar o banco de dados local.
* `appfleshi/`: Pacote principal da aplicação.
  * `models.py`: Definição das tabelas e esquemas do banco de dados (Usuários, Posts).
  * `routes.py`: Controle das rotas e regras de negócio da aplicação.
  * `forms.py`: Estruturação e validação dos formulários web.
  * `templates/`: Arquivos HTML estruturados utilizando Jinja2 e componentes do Bootstrap.
  * `static/`: Arquivos estáticos (imagens de upload e mídias padrão).

---

## 🔧 Como Executar o Projeto Localmente

### Pré-requisitos
Ter o **Python 3.x** instalado em sua máquina.

### Passo a Passo

1. **Clone o repositório:**
```bash
   git clone [https://github.com/Ygorfnascimento/Rede_Social-Flesh.git](https://github.com/Ygorfnascimento/Rede_Social-Flesh.git)
   cd Rede_Social-Flesh
```
2. **Crie e ative um ambiente virtual (Opcional, mas recomendado):**
```bash
python -m venv venv
   # No Windows:
   .\venv\Scripts\activate
   # No Linux/Mac:
   source venv/bin/activate
```
3. **Instale as dependências básicas (Flask, Flask-SQLAlchemy, Flask-WTF):**
```bash
pip install flask flask-sqlalchemy flask-wtf email-validator
```
4. **Inicialize o Banco de Dados:
Execute o script para criar o arquivo de banco de dados e as tabelas necessárias:**
```bash
python create_database.py
```
5. **Execute a aplicação:**
```bash
python app.py
```
6. **Acesse ``` http://127.0.0.1:5000 ``` no seu navegador para testar a rede social!**
