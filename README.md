````markdown
# 🛡️ CryptoStegano Pro — Suite Cybersécurité Professionnelle

<div align="center">

![Version](https://img.shields.io/badge/Version-2.0.0-00ffe0?style=for-the-badge&logo=shield)
![Java](https://img.shields.io/badge/Java-17+-orange?style=for-the-badge&logo=java)
![JavaFX](https://img.shields.io/badge/JavaFX-21-blue?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Stable-00ff9d?style=for-the-badge)
![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux%20%7C%20macOS-7700ff?style=for-the-badge)

<br/>

**Suite de cybersécurité tout-en-un — Chiffrement post-quantique · Stéganographie LSB · OSINT · NIDS · IA Gemini**

[🚀 Explorer](#-modules) • [⬇️ Télécharger](#-installation) • [📖 Documentation](#-documentation) • [🤝 Contribuer](#-contribuer)

</div>

---

## 📋 Table des Matières

- [Présentation](#-présentation)
- [Fonctionnalités](#-fonctionnalités)
- [Modules](#-modules)
- [Stack Technique](#-stack-technique)
- [Installation](#-installation)
- [Utilisation](#-utilisation)
- [Configuration](#-configuration)
- [Comparatif](#-comparatif)
- [Architecture](#-architecture)
- [Contribuer](#-contribuer)
- [Sécurité](#-sécurité)
- [FAQ](#-faq)
- [Roadmap](#-roadmap)
- [Changelog](#-changelog)
- [Auteur](#-auteur)
- [Licence](#-licence)

---

## 🔭 Présentation

**CryptoStegano Pro** est une suite de cybersécurité professionnelle développée en **Java 17 + JavaFX 21**, regroupant en une seule application :

- 🔐 Chiffrement **AES-256-GCM**, **RSA-4096**, **Kyber-1024 (post-quantique)**
- 🖼️ Stéganographie **LSB** avec double blindage AES
- 📡 Analyse réseau **Nmap intégré** + cartographie **Vis.js**
- 🌐 Reconnaissance **OSINT** multi-sources (WHOIS, DNS, GeoIP, Shodan, Leaks)
- 🚨 Détection d'intrusion **NIDS** temps réel avec règles Snort
- 🤖 Assistant IA **Gemini Pro** intégré
- 🛠️ Utilitaires avancés (Hex Viewer, Hash Calculator, File Comparator...)

> ⚠️ **Usage éthique uniquement.** Conçu pour la sécurité de vos propres systèmes, la formation, les CTF et la recherche académique.

---

## ✨ Fonctionnalités

| Catégorie | Détail |
|-----------|--------|
| 🔒 **Crypto** | AES-256-GCM, RSA-4096, Kyber-1024, 3DES, Blowfish, César, Vigenère |
| 🖼️ **Stégano** | Injection LSB PNG/BMP, extraction CRC32, stéganalyse Chi², multi-canaux 1-4 bits |
| 📡 **Réseau** | ARP scan, Nmap 8 profils, cartographie interactive, monitoring temps réel |
| 🌐 **OSINT** | WHOIS, DNS records, IP GeoIP, Leak lookup, Shodan API |
| 🚨 **NIDS** | SYN flood, ARP spoofing, port scan, SSH brute force, règles custom Snort |
| 🤖 **IA** | Gemini Pro, typewriter effect, historique, mode hacker terminal |
| 🛠️ **Outils** | Hex Viewer, Hash MD5/SHA/BLAKE2, File Diff, Logs centralisés, Kiosk mode |

---

## 📦 Modules

### Module 01 — Chiffrement Avancé

```java
// AES-256-GCM Authenticated Encryption
public class CipherEngine implements ICipher {
    private static final String ALGO = "AES/GCM/NoPadding";
    private static final int TAG_LEN = 128;

    @Override
    public byte[] encrypt(byte[] data) {
        byte[] iv = generateIV(12);
        GCMParameterSpec spec = new GCMParameterSpec(TAG_LEN, iv);
        Cipher c = Cipher.getInstance(ALGO);
        c.init(Cipher.ENCRYPT_MODE, masterKey, spec);
        return concat(iv, c.doFinal(data));
    }
}
```

| Algorithme | Type | Niveau | Standard |
|------------|------|--------|----------|
| AES-256-GCM | Symétrique authentifié | ⚡ MAXIMUM | NIST FIPS 197 |
| RSA-4096 | Asymétrique | ⚡ MAXIMUM | PKCS#1 v2.2 |
| Kyber-1024 | Post-Quantique | ⚛️ QUANTUM | NIST PQC 2024 |
| 3DES / Blowfish | Symétrique | 🟡 LEGACY | FIPS 46-3 |
| César / Vigenère | Classique | 📚 CLASSIC | Éducatif / CTF |

---

### Module 02 — Stéganographie LSB

```
Image PNG/BMP (24-bit)
       │
       ▼
┌──────────────┐     ┌─────────────────┐
│  Payload     │────▶│  AES-256 Encrypt │
│  (texte/     │     │  (double blind)  │
│   fichier)   │     └────────┬────────┘
└──────────────┘              │
                              ▼
                    ┌─────────────────┐
                    │  LSB Injection  │
                    │  R[0] G[0] B[0] │
                    │  par pixel      │
                    └────────┬────────┘
                              │
                              ▼
                    Image stégano (=visuel)
```

**Capacités :**
- Support **PNG 24-bit** et **BMP** sans perte visuelle
- Modes **1 à 4 bits** par canal LSB
- **Checksum CRC32** intégré pour extraction sans corruption
- **Stéganalyse Chi²** et RS-analysis pour détection
- Calcul automatique de la **capacité maximale**

---

### Module 03 — Analyse Réseau

**Profils Nmap disponibles :**

```bash
# Quick scan
nmap -T4 -F 192.168.1.0/24

# Full scan avec détection OS
nmap -sV -O -T4 192.168.1.0/24

# Stealth SYN scan
nmap -sS -T2 192.168.1.0/24

# Vulnerability scan (NSE)
nmap --script vuln 192.168.1.0/24

# Scan agressif
nmap -A -T5 192.168.1.0/24
```

**Fonctionnalités réseau :**
- 🗺️ Cartographie **Vis.js** interactive (drag-drop, clustering, export PNG)
- 📡 Scan **ARP/LAN** avec résolution DNS et fabricants MAC
- 📊 Stats temps réel : latence, RTT, hôtes actifs, services exposés
- 🔍 Fingerprinting OS avec niveau de confiance

---

### Module 04 — OSINT Intelligence

```
Cible (domaine / IP / email)
           │
    ┌──────┴──────┐
    │             │
    ▼             ▼
┌────────┐  ┌──────────┐
│ WHOIS  │  │DNS Records│
│Registrar│  │A MX TXT  │
│NS, dates│  │CNAME SOA │
└────────┘  └──────────┘
    │             │
    ▼             ▼
┌────────┐  ┌──────────┐
│GeoIP   │  │Leak Check│
│Pays ASN│  │HIBP API  │
│GPS Org │  │Bases dump│
└────────┘  └──────────┘
           │
           ▼
      ┌──────────┐
      │  Shodan  │
      │CVEs ports│
      │Bannières │
      └──────────┘
```

---

### Module 05 — NIDS (Network Intrusion Detection)

**Attaques détectées :**

| Attaque | Méthode | Niveau |
|---------|---------|--------|
| SYN Flood | Signature + seuil pkt/s | 🔴 CRITIQUE |
| ARP Spoofing | Analyse tables ARP | 🔴 CRITIQUE |
| Port Scanning | Heuristique multi-ports | 🟡 WARNING |
| SSH Brute Force | Compteur tentatives | 🟡 WARNING |
| ICMP Flood / Ping Sweep | Signature ICMP | 🔵 INFO |
| DNS Amplification | Ratio trafic UDP | 🔴 CRITIQUE |

**Export :** CSV · JSON · PCAP

---

### Module 06 — Assistant IA Gemini

- 🤖 **Gemini Pro** via Google API
- ✨ Effet **typewriter** caractère par caractère
- 💾 **Historique** des conversations
- 🖥️ Mode **terminal hacker** monospace
- 🎯 Spécialisé **cybersécurité & cryptographie**

---

### Module 07 — Utilitaires Avancés

| Outil | Description |
|-------|-------------|
| 📄 File Comparator | Diff binaire/texte + distance Levenshtein |
| 🔢 Hex Viewer Pro | Édition hex + recherche de patterns binaires |
| 🔑 Hash Calculator | MD5, SHA-1/256/512, BLAKE2 + comparateur |
| 📜 Logs Centralisés | Filtres + recherche full-text + export multi-format |
| ⚙️ Automatisation | Pipeline scan → chiffrement → rapport |
| 🎯 Kiosk Mode | Interface épurée pour présentations |

---

## 🛠️ Stack Technique

```
┌─────────────────────────────────────────────────────────────┐
│                    CryptoStegano Pro v2.0                   │
├──────────────┬──────────────┬──────────────┬────────────────┤
│   UI Layer   │  Crypto Core │ Network Core │   AI / APIs    │
│              │              │              │                │
│  JavaFX 21   │Bouncy Castle │   Pcap4J     │  Gemini API    │
│Scene Builder │  AES/RSA     │   Nmap 7.9+  │  Shodan API    │
│  Vis.js      │  Kyber-KEM   │   Vis.js     │  Formspree     │
│  JFreeChart  │  1024        │              │                │
├──────────────┴──────────────┴──────────────┴────────────────┤
│                      Build & Test                           │
│            Apache Maven · JUnit 5 · Java 17+               │
└─────────────────────────────────────────────────────────────┘
```

**Dépendances principales :**

```xml
<!-- pom.xml -->
<dependencies>

    <!-- JavaFX -->
    <dependency>
        <groupId>org.openjfx</groupId>
        <artifactId>javafx-controls</artifactId>
        <version>21.0.2</version>
    </dependency>

    <!-- Bouncy Castle (Crypto + Kyber) -->
    <dependency>
        <groupId>org.bouncycastle</groupId>
        <artifactId>bcprov-jdk18on</artifactId>
        <version>1.78.1</version>
    </dependency>

    <!-- Pcap4J (Network Capture) -->
    <dependency>
        <groupId>org.pcap4j</groupId>
        <artifactId>pcap4j-core</artifactId>
        <version>2.0.0-alpha.6</version>
    </dependency>

    <!-- JFreeChart -->
    <dependency>
        <groupId>org.jfree</groupId>
        <artifactId>jfreechart</artifactId>
        <version>1.5.4</version>
    </dependency>

    <!-- JUnit 5 -->
    <dependency>
        <groupId>org.junit.jupiter</groupId>
        <artifactId>junit-jupiter</artifactId>
        <version>5.10.2</version>
        <scope>test</scope>
    </dependency>

</dependencies>
```

---

## 📥 Installation

### Prérequis

| Outil | Version minimale | Obligatoire |
|-------|-----------------|-------------|
| Java JDK | 17+ | ✅ Oui |
| Nmap | 7.9+ | ⚠️ Recommandé |
| Pcap / WinPcap | Dernière | ⚠️ Pour NIDS |
| Shodan API Key | — | ❌ Optionnel |
| Gemini API Key | — | ❌ Optionnel |

---

### Option 1 — Exécutable Windows (.exe)

```bash
# 1. Télécharger le .exe depuis les Releases GitHub

# 2. Vérifier l'intégrité (SHA-256)
certutil -hashfile CryptoSteganoPro-2.0.0.exe SHA256

# 3. Lancer
CryptoSteganoPro-2.0.0.exe
```

---

### Option 2 — JAR universel (Linux / macOS / Windows)

```bash
# 1. Cloner le dépôt
git clone https://github.com/samou2/CryptoSteganoPro.git
cd CryptoSteganoPro

# 2. Compiler
mvn clean package -DskipTests

# 3. Lancer
java -jar target/CryptoSteganoPro-2.0.0.jar
```

---

### Option 3 — Compilation depuis les sources

```bash
# 1. Cloner
git clone https://github.com/samou2/CryptoSteganoPro.git
cd CryptoSteganoPro

# 2. Vérifier Java
java -version    # Java 17+ requis

# 3. Build complet avec tests
mvn clean verify

# 4. Générer le .exe (Windows, launch4j requis)
mvn package -P windows-exe

# 5. Lancer en développement
mvn javafx:run
```

---

### Installation Nmap (recommandé)

```bash
# Windows (winget)
winget install Insecure.Nmap

# Ubuntu / Debian
sudo apt install nmap

# Fedora / RHEL
sudo dnf install nmap

# macOS (Homebrew)
brew install nmap

# Vérifier
nmap --version
```

---

## 🚀 Utilisation

### Démarrage rapide (5 étapes)

```
1️⃣  TÉLÉCHARGEZ   →  CryptoSteganoPro-2.0.0.exe
2️⃣  LANCEZ        →  Double-clic ou java -jar
3️⃣  CONFIGUREZ    →  Clés API dans Paramètres (optionnel)
4️⃣  ANALYSEZ      →  Sélectionnez votre module
5️⃣  EXPORTEZ      →  PDF / JSON / CSV / PCAP
```

---

### Chiffrement — Exemple API Java

```java
// Chiffrement AES-256-GCM
CipherEngine engine = new CipherEngine(Algorithm.AES_GCM);
engine.generateKey(256);
byte[] encrypted = engine.encrypt("Message secret".getBytes());
byte[] decrypted = engine.decrypt(encrypted);

// Chiffrement post-quantique Kyber-1024
KyberEngine kyber = new KyberEngine(SecurityLevel.KYBER_1024);
KyberKeyPair keyPair = kyber.generateKeyPair();
byte[] ciphertext = kyber.encapsulate(keyPair.getPublicKey());
```

---

### Stéganographie — Exemple

```java
// Injection LSB
SteganographyEngine steg = new SteganographyEngine();
steg.setImage("photo.png");
steg.setBitsPerChannel(2);        // 1 à 4 bits
steg.setPassword("motdepasse");   // Double blindage AES

steg.embed("Message caché".getBytes());
steg.save("photo_steg.png");

// Extraction
byte[] extracted = steg.extract("photo_steg.png", "motdepasse");
System.out.println(new String(extracted));
// → "Message caché"

// Analyse de capacité
long capacity = steg.getCapacity("photo.png", 2);
System.out.println("Capacité max : " + capacity + " octets");
```

---

### Scan Réseau — Exemple

```java
// Scan ARP du réseau local
NetworkScanner scanner = new NetworkScanner();
List<Host> hosts = scanner.arpScan("192.168.1.0/24");
hosts.forEach(h -> System.out.println(h.getIp() + " — " + h.getMac()));

// Scan Nmap avancé
NmapRunner nmap = new NmapRunner();
nmap.setProfile(NmapProfile.FULL_OS_DETECTION);
nmap.setTarget("192.168.1.5");
ScanResult result = nmap.run();
result.getPorts().forEach(p ->
    System.out.println(p.getNumber() + "/" + p.getProtocol()
        + " — " + p.getService())
);
```

---

### OSINT — Exemple

```java
// Lookup complet d'un domaine
OsintEngine osint = new OsintEngine();
osint.setShodanApiKey("YOUR_KEY");

WhoisResult  whois  = osint.whois("example.com");
DnsResult    dns    = osint.dnsLookup("example.com");
GeoResult    geo    = osint.geoIP("93.184.216.34");
LeakResult   leaks  = osint.checkLeaks("user@example.com");
ShodanResult shodan = osint.shodanLookup("93.184.216.34");
```

---

## ⚙️ Configuration

### Fichier `config.properties`

```properties
# ─── Clés API (optionnelles) ───────────────────────────────
shodan.api.key=YOUR_SHODAN_KEY
gemini.api.key=YOUR_GEMINI_KEY

# ─── NIDS ──────────────────────────────────────────────────
nids.interface=eth0
nids.rules.path=/etc/snort/rules/local.rules
nids.syn.threshold=500
nids.icmp.threshold=200
nids.ssh.brute.threshold=50

# ─── Réseau ────────────────────────────────────────────────
nmap.path=/usr/bin/nmap
network.scan.timeout=30
network.arp.range=192.168.1.0/24

# ─── Stéganographie ────────────────────────────────────────
steg.default.bits=2
steg.output.format=PNG
steg.aes.enabled=true

# ─── Interface ─────────────────────────────────────────────
ui.theme=dark
ui.language=fr
ui.kiosk.mode=false

# ─── Logs ──────────────────────────────────────────────────
log.level=INFO
log.export.path=./logs/
log.max.size=50MB
```

---

### Variables d'environnement

```bash
# Linux / macOS
export CSP_SHODAN_KEY="your_key_here"
export CSP_GEMINI_KEY="your_key_here"
export CSP_NMAP_PATH="/usr/bin/nmap"

# Windows (PowerShell)
$env:CSP_SHODAN_KEY="your_key_here"
$env:CSP_GEMINI_KEY="your_key_here"
```

---

## 📊 Comparatif

| Fonctionnalité | CryptoStegano Pro | Wireshark | OpenSSL CLI | Kali Tools |
|----------------|:-----------------:|:---------:|:-----------:|:----------:|
| Interface graphique JavaFX | ✅ | ✅ | ❌ | ❌ |
| Stéganographie LSB intégrée | ✅ | ❌ | ❌ | ⚠️ |
| OSINT multi-sources | ✅ | ❌ | ❌ | ⚠️ |
| NIDS règles custom | ✅ | ⚠️ | ❌ | ✅ |
| Assistant IA intégré | ✅ | ❌ | ❌ | ❌ |
| Chiffrement post-quantique Kyber | ✅ | ❌ | ❌ | ❌ |
| Stéganalyse Chi-carré | ✅ | ❌ | ❌ | ⚠️ |
| Cartographie réseau visuelle | ✅ | ❌ | ❌ | ❌ |
| Open source | ✅ | ✅ | ✅ | ✅ |
| Application tout-en-un | ✅ | ❌ | ❌ | ❌ |

> ✅ Complet · ⚠️ Partiel / outil séparé · ❌ Non disponible

---

## 🏗️ Architecture

```
CryptoSteganoPro/
│
├── 📁 src/main/java/com/csp/
│   ├── 📁 cipher/                  # Module chiffrement
│   │   ├── CipherEngine.java
│   │   ├── AesGcmCipher.java
│   │   ├── RsaCipher.java
│   │   ├── KyberEngine.java
│   │   └── ClassicCipher.java
│   │
│   ├── 📁 stegano/                 # Module stéganographie
│   │   ├── SteganographyEngine.java
│   │   ├── LsbInjector.java
│   │   ├── LsbExtractor.java
│   │   └── ChiSquareAnalysis.java
│   │
│   ├── 📁 network/                 # Module réseau
│   │   ├── NetworkScanner.java
│   │   ├── NmapRunner.java
│   │   ├── ArpScanner.java
│   │   └── NetworkMapper.java
│   │
│   ├── 📁 osint/                   # Module OSINT
│   │   ├── OsintEngine.java
│   │   ├── WhoisLookup.java
│   │   ├── DnsResolver.java
│   │   ├── GeoIPService.java
│   │   ├── LeakChecker.java
│   │   └── ShodanClient.java
│   │
│   ├── 📁 nids/                    # Module NIDS
│   │   ├── NidsEngine.java
│   │   ├── PacketCapture.java
│   │   ├── RuleParser.java
│   │   └── AlertManager.java
│   │
│   ├── 📁 ai/                      # Module IA
│   │   ├── GeminiClient.java
│   │   └── ChatSession.java
│   │
│   ├── 📁 tools/                   # Utilitaires
│   │   ├── HexViewer.java
│   │   ├── HashCalculator.java
│   │   ├── FileComparator.java
│   │   └── LogManager.java
│   │
│   ├── 📁 ui/                      # Interface JavaFX
│   │   ├── MainController.java
│   │   ├── DashboardController.java
│   │   └── controllers/
│   │
│   └── 📁 core/                    # Noyau applicatif
│       ├── AppConfig.java
│       ├── EventBus.java
│       └── MainApp.java
│
├── 📁 src/main/resources/
│   ├── 📁 fxml/                    # Layouts JavaFX
│   ├── 📁 css/                     # Styles dark theme
│   ├── 📁 rules/                   # Règles NIDS par défaut
│   └── config.properties
│
├── 📁 src/test/                    # Tests JUnit 5
├── 📁 docs/                        # Documentation
├── 📄 pom.xml
├── 📄 README.md
├── 📄 CONTRIBUTING.md
├── 📄 CHANGELOG.md
└── 📄 LICENSE
```

---

## 🤝 Contribuer

Les contributions sont les bienvenues ! 🎉

### Comment contribuer

```bash
# 1. Fork du projet sur GitHub

# 2. Cloner votre fork
git clone https://github.com/VOTRE_USERNAME/CryptoSteganoPro.git
cd CryptoSteganoPro

# 3. Créer une branche feature
git checkout -b feature/ma-nouvelle-fonctionnalite

# 4. Développer + tester
mvn test

# 5. Commit (format conventionnel)
git commit -m "feat(cipher): ajouter support ChaCha20-Poly1305"

# 6. Push
git push origin feature/ma-nouvelle-fonctionnalite

# 7. Ouvrir une Pull Request sur GitHub
```

### Conventions de commit

```
feat(module):     Nouvelle fonctionnalité
fix(module):      Correction de bug
docs:             Documentation
style:            Formatage (pas de logique)
refactor(module): Refactoring
test:             Ajout de tests
chore:            Maintenance, dépendances
```

### Standards de code Java

```java
// ✅ Bien — respecter ces conventions
public class AesGcmCipher implements ICipher {

    private static final int IV_LENGTH = 12;      // Constantes SCREAMING_SNAKE
    private final SecretKey secretKey;             // Champs final quand possible

    public byte[] encrypt(byte[] plaintext) {      // Méthodes en camelCase
        Objects.requireNonNull(plaintext, "Plaintext cannot be null");
        // ...
    }
}

// ✅ Tests obligatoires pour tout nouveau module
@Test
@DisplayName("AES-GCM: decrypted output should match original plaintext")
void testAesGcmRoundTrip() {
    byte[] original  = "test".getBytes(StandardCharsets.UTF_8);
    byte[] encrypted = engine.encrypt(original);
    byte[] decrypted = engine.decrypt(encrypted);
    assertArrayEquals(original, decrypted);
}
```

---

## 🔒 Sécurité

### Signaler une vulnérabilité

> ⚠️ **Ne pas créer d'issue publique** pour des vulnérabilités de sécurité.

Envoyez un email à : **samoumegharba210@gmail.com**

**Format du rapport :**

```
Sujet  : [SECURITY] Description courte
Corps  :
  - Description de la vulnérabilité
  - Étapes de reproduction
  - Impact potentiel
  - Suggestion de correction (optionnel)
```

**Délai de réponse :** 48h maximum

### Bonnes pratiques intégrées

- ✅ Aucune clé hardcodée dans le code source
- ✅ Secrets via variables d'environnement / config externe
- ✅ Inputs validés et sanitisés
- ✅ Dépendances auditées via `mvn dependency:check`
- ✅ Mode least-privilege pour les captures réseau

---

## ❓ FAQ

<details>
<summary><strong>Quels systèmes d'exploitation sont supportés ?</strong></summary>

Windows 10/11, macOS 12+ et Linux (Ubuntu, Fedora, Arch) avec **Java 17+**.
Le JAR universel fonctionne sur toute plateforme JVM.
Le `.exe` est un wrapper natif Windows via launch4j.
</details>

<details>
<summary><strong>Nmap doit-il être installé séparément ?</strong></summary>

**Oui**, Nmap doit être dans le `PATH` pour les scans avancés (OS detection, NSE scripts, stealth SYN).
Les scans **ARP et ping basiques** fonctionnent sans Nmap via Pcap4J.
</details>

<details>
<summary><strong>Le chatbot nécessite-t-il une connexion internet ?</strong></summary>

Uniquement **Gemini** et les fonctions **OSINT en ligne**.
Chiffrement, stéganographie, NIDS et scan réseau local fonctionnent **100% hors-ligne**.
</details>

<details>
<summary><strong>L'application est-elle légale à utiliser ?</strong></summary>

CryptoStegano Pro est conçu pour un usage **éthique** :
sécurité de vos propres systèmes, formation, CTF, recherche.
L'utilisation sur des systèmes tiers **sans autorisation explicite est illégale**.
</details>

<details>
<summary><strong>Comment importer mes règles Snort personnalisées ?</strong></summary>

```
Paramètres → NIDS → Règles → Importer fichier .rules
```
Le moteur accepte le format **Snort 3** et **Suricata** (sous-ensemble compatible).
</details>

<details>
<summary><strong>Comment obtenir une clé API Shodan ?</strong></summary>

1. Créer un compte sur [shodan.io](https://www.shodan.io)
2. Dashboard → My Account → API Key
3. Coller dans `config.properties` → `shodan.api.key=...`

Plan gratuit disponible (1 requête/seconde).
</details>

<details>
<summary><strong>Comment contribuer au projet ?</strong></summary>

Le projet est open-source sur GitHub.
Fork, pull requests et issues sont bienvenus.
Consultez `CONTRIBUTING.md` pour les conventions Java et l'architecture des modules.
</details>

---

## 📈 Roadmap

- [ ] **v2.1** — Support ChaCha20-Poly1305
- [ ] **v2.1** — Dashboard métriques réseau temps réel avancé
- [ ] **v2.2** — Plugin system pour modules tiers
- [ ] **v2.2** — Support stéganographie audio (WAV LSB)
- [ ] **v2.3** — Export rapports PDF automatisés
- [ ] **v3.0** — Mode CLI headless pour automatisation CI/CD
- [ ] **v3.0** — Support CRYSTALS-Dilithium (signatures post-quantiques)

---

## 📄 Changelog

### v2.0.0 — 2025

- ✨ Ajout module **NIDS** avec règles Snort custom
- ✨ **Kyber-1024** post-quantique (NIST PQC 2024)
- ✨ **Assistant IA Gemini Pro** intégré
- ✨ **Stéganalyse Chi²** et RS-analysis
- ✨ Mode **multi-canaux LSB** (1-4 bits)
- ✨ **Hex Viewer Pro** et **Hash Calculator**
- ✨ Pipeline **automatisation** configurable
- 🔧 Refactoring architecture modulaire complète
- 🔧 Migration JavaFX 21
- 🐛 Correction extraction CRC32 sur grands fichiers

### v1.0.0 — 2024

- 🚀 Release initiale : AES, RSA, LSB, Nmap, OSINT basique

---

## 👨‍💻 Auteur

<div align="center">

**Samou Megharba**

[![Portfolio](https://img.shields.io/badge/Portfolio-samoumegharba.vercel.app-00ffe0?style=for-the-badge&logo=vercel)](https://samoumegharba.vercel.app)
[![GitHub](https://img.shields.io/badge/GitHub-samou2-181717?style=for-the-badge&logo=github)](https://github.com/samou2)
[![Email](https://img.shields.io/badge/Email-samoumegharba210%40gmail.com-EA4335?style=for-the-badge&logo=gmail)](mailto:samoumegharba210@gmail.com)

🇩🇿 Algérie — UTC+1 — Réponse sous 24h

</div>

---

## 📜 Licence

```
MIT License

Copyright (c) 2025 Samou Megharba

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

<div align="center">

⭐ **Si ce projet vous est utile, n'oubliez pas de lui donner une étoile !** ⭐

<br/>

**CryptoStegano Pro** — Fait avec ❤️ par [Samou Megharba](https://samoumegharba.vercel.app) 🇩🇿

<br/>

`v2.0.0` · `Java 17` · `JavaFX 21` · `MIT License`

</div>
````
