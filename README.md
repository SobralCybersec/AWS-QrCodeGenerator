<div align="center">

<h1 align="center">
  <img src="https://i.imgur.com/2mPtxE5.png" width="30" />
  AWS QR Code Generator
</h1>

* API REST para geração de QR Codes
* Backend em Java com Spring Boot
* Armazenamento automático na AWS S3
* Arquitetura Hexagonal (Ports & Adapters)
* Containerização com Docker


---

<h1 align="center">
  <img src="https://i.imgur.com/VN6wG7g.gif" width="30"/>
  Demonstração
</h1>

https://github.com/user-attachments/assets/b88caca6-da3e-4939-8084-7b61da3bf68d

---

<h1 align="center">
  <img src="https://i.imgur.com/vSRgNpa.gif" width="30"/>
  Documentação
</h1>

Sistema de geração dinâmica de QR Codes com upload automático para AWS S3. Ideal para integração em sistemas que necessitam de geração de códigos QR a partir de URLs.

</div>

---

<h1 align="center">
  <img src="https://i.imgur.com/dwyUWDH.gif" width="30"/> Features
</h1>

* **Geração de QR Codes**: criação de QR Codes a partir de URLs
* **Upload Automático**: armazenamento direto na AWS S3
* **API REST**: endpoint simples e eficiente
* **Arquitetura Hexagonal**: separação clara entre domínio e infraestrutura
* **Containerização**: suporte completo para Docker
* **Build Otimizado**: gerenciamento de dependências com Maven

---

<h1 align="center">
  <img src="https://i.imgur.com/eu3StDB.gif" width="30"/> Tech Stack
</h1>

<p align="center">
  <img src="https://go-skill-icons.vercel.app/api/icons?i=java,spring,maven,aws,docker&size=64" />
</p>

---

* Java 17
* Spring Boot 3.5.8
* Maven 3.9.6
* ZXing 3.5.0 (geração de QR Codes)
* AWS SDK 2.25.61 (integração com S3)
* Docker

---

<h1 align="center">
  <img src="https://cdn-icons-png.flaticon.com/512/1157/1157109.png" width="30"/> Architecture
</h1>

<div align="center">
  
• O projeto segue **Arquitetura Hexagonal (Ports & Adapters)**.

• Fundamentos com SOLID e Clean Code.

• Separação clara entre domínio, portas e adaptadores.
</div>

---

<h1 align="center">
  <img src="https://i.imgur.com/Jvttz1s.png" width="30"/> System Flow | Fluxo
</h1>

<div align="center">
  
```
Cliente envia URL via POST
        ↓
Service gera QR Code (ZXing)
        ↓
Adapter faz upload para S3
        ↓
Sistema retorna URL pública do QR Code
        ↓
Cliente acessa imagem na AWS S3
```
</div>

---

<h1 align="center">
  <img src="https://i.imgur.com/rNaTn43.png" width="30"/> Estrutura do Projeto
</h1>

```
qrcodegenerator/
├── adapter/         # Implementações de infraestrutura (S3)
├── controller/      # Endpoints REST
├── dto/
│   ├── request/     # DTOs de entrada
│   └── response/    # DTOs de saída
├── entity/          # Entidades de domínio
├── ports/           # Interfaces (contratos)
├── service/         # Lógica de negócio
└── utils/           # Utilitários
```

---

<h1 align="center">
  <img src="https://i.imgur.com/PFZmPWb.gif" width="30"/> Como Executar
</h1>

**Pré-requisitos**

* Java 17+
* Maven 3.9+
* Conta AWS com acesso ao S3
* Docker (opcional)

**Configuração**

```bash
# Clone o repositório
git clone <seu-repositorio>
cd qrcodegenerator

# Configure variáveis de ambiente
export AWS_ACCESS_KEY_ID=<sua-access-key>
export AWS_SECRET_ACCESS_KEY=<sua-secret-key>
export AWS_REGION=us-east-2
export AWS_BUCKET_NAME=qrcodestoragesatushi
```

**Executar Localmente**

```bash
mvn clean package
java -jar target/qrcode-0.0.1-SNAPSHOT.jar
```

**Executar com Docker**

```bash
docker build -t qrcode-generator \
  --build-arg AWS_ACCESS_KEY_ID=<sua-access-key> \
  --build-arg AWS_SECRET_ACCESS_KEY=<sua-secret-key> \
  .

docker run -p 8080:8080 qrcode-generator
```

---

<h1 align="center">
  <img src="https://cdn-icons-png.flaticon.com/512/2103/2103633.png" width="30"/> API Endpoint
</h1>

**POST /qrcode**

```json
{
  "qrcodeurl": "https://exemplo.com"
}
```

**Resposta (200 OK)**

```json
{
  "url": "https://s3.us-east-2.amazonaws.com/qrcodestoragesatushi/qrcode-1234567890.png"
}
```

---

<h1 align="center">
  <img src="https://i.imgur.com/O7HwCZt.gif" width="30"/> Roadmap
</h1>

* [x] Geração de QR Codes
* [x] Upload para AWS S3
* [x] API REST
* [x] Arquitetura Hexagonal
* [x] Containerização Docker

---

<h1 align="center"><img src="https://i.imgur.com/6nSJzZ2.gif" width="35"/> Referências e Documentações utilizadas</h1>

<h2 align="center">
  
**Spring Boot Docs**: [Link](https://docs.spring.io/spring-boot/index.html)  <img src="https://go-skill-icons.vercel.app/api/icons?i=spring&size=64" width="40" />

</h2>

<h2 align="center">
  
**AWS S3 SDK**: [Link](https://docs.aws.amazon.com/sdk-for-java/latest/developer-guide/examples-s3.html)  <img src="https://go-skill-icons.vercel.app/api/icons?i=aws&size=64" width="40" />

</h2>

<h2 align="center">
  
**ZXing Library**: [Link](https://github.com/zxing/zxing)  <img src="https://cdn-icons-png.flaticon.com/512/714/714489.png" width="40" />

</h2>

<h2 align="center">
  
**Maven**: [Link](https://maven.apache.org/guides/)  <img src="https://go-skill-icons.vercel.app/api/icons?i=maven&size=32" width="40" />

</h2>

<h2 align="center">
  
**Docker**: [Link](https://docs.docker.com/)  <img src="https://go-skill-icons.vercel.app/api/icons?i=docker&size=32" width="40" />

</h2>
