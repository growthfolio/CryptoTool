# 🔐 CryptoTool - Biblioteca Educacional de Criptografia

## 🎯 Objetivo de Aprendizado
Ferramenta educacional desenvolvida em Go para estudar **algoritmos criptográficos** clássicos e modernos. Implementa **AES**, **RSA**, **ECC**, **SHA-256** e outros algoritmos, servindo como biblioteca reutilizável e plataforma de aprendizado em segurança da informação.

## 🛠️ Tecnologias Utilizadas
- **Linguagem:** Go
- **Criptografia:** Algoritmos simétricos e assimétricos
- **Hashing:** SHA-256, HMAC, scrypt
- **Curvas elípticas:** ECC, ECDSA
- **Qualidade:** SonarCloud integration
- **Testes:** Unit testing para validação

## 🚀 Demonstração
```go
// Exemplo de uso da biblioteca
import "github.com/growthfolio/CryptoTool/pkg/cryptoLib"

// Criptografia AES
encrypted, err := cryptoLib.AESEncrypt(plaintext, key)
decrypted, err := cryptoLib.AESDecrypt(encrypted, key)

// Assinatura digital ECDSA
signature, err := cryptoLib.ECDSASign(message, privateKey)
valid := cryptoLib.ECDSAVerify(message, signature, publicKey)
```

## 📊 Status de Implementação

### ✅ Criptografia Simétrica
- [x] **AES (Advanced Encryption Standard)** - Padrão moderno
- [x] **ChaCha20** - Stream cipher seguro
- [x] **Blowfish** - Algoritmo clássico (obsoleto)
- [x] **DES/3DES** - Algoritmos históricos

### ✅ Criptografia Assimétrica
- [x] **RSA** - Rivest-Shamir-Adleman
- [x] **ECC** - Elliptic Curve Cryptography

### ✅ Funções Hash
- [x] **SHA-256** - Secure Hash Algorithm
- [x] **HMAC** - Hash-based Message Authentication

### ✅ Assinaturas Digitais
- [x] **ECDSA** - Elliptic Curve Digital Signature

### ✅ Derivação de Chaves
- [x] **scrypt** - Password-based key derivation

### 🔄 Em Desenvolvimento
- [ ] **ElGamal** - Criptografia assimétrica
- [ ] **SHA-3** - Nova geração de hash
- [ ] **PBKDF2** - Key derivation function
- [ ] **RC4** - Stream cipher (educacional)

## 💡 Principais Aprendizados

### 🔒 Fundamentos Criptográficos
- **Criptografia simétrica vs assimétrica:** Diferenças e aplicações
- **Funções hash:** Integridade e autenticação
- **Assinaturas digitais:** Não-repúdio e autenticidade
- **Key derivation:** Geração segura de chaves

### 🏗️ Implementação Segura
- **Constant-time operations:** Prevenção de timing attacks
- **Secure random generation:** Entropia adequada
- **Memory management:** Limpeza de dados sensíveis
- **Error handling:** Tratamento seguro de falhas

### 📚 Algoritmos Estudados
- **AES:** Substituição-permutação, modos de operação
- **RSA:** Matemática modular, padding schemes
- **ECC:** Curvas elípticas, pontos e operações
- **SHA-256:** Merkle-Damgård construction

## 🧠 Conceitos Técnicos Estudados

### 1. **Implementação AES**
```go
// Estrutura do algoritmo AES
type AES struct {
    key        []byte
    rounds     int
    roundKeys  [][]byte
}

func (a *AES) Encrypt(plaintext []byte) ([]byte, error) {
    // SubBytes, ShiftRows, MixColumns, AddRoundKey
    return a.processBlock(plaintext, true)
}
```

### 2. **Curvas Elípticas (ECC)**
```go
// Operações em curvas elípticas
type Point struct {
    X, Y *big.Int
}

func (p *Point) Add(q *Point, curve *Curve) *Point {
    // Adição de pontos na curva elíptica
    return pointAdd(p, q, curve)
}
```

### 3. **Geração Segura de Chaves**
```go
// Derivação de chaves com scrypt
func DeriveKey(password, salt []byte, keyLen int) ([]byte, error) {
    return scrypt.Key(password, salt, 32768, 8, 1, keyLen)
}
```

## 🚧 Desafios Enfrentados
1. **Implementação segura:** Evitar vulnerabilidades criptográficas
2. **Performance:** Otimização de algoritmos complexos
3. **Compatibilidade:** Interoperabilidade com padrões
4. **Testing:** Validação contra test vectors conhecidos
5. **Documentation:** Explicação clara de conceitos complexos

## 📚 Recursos Utilizados
- [Applied Cryptography - Bruce Schneier](https://www.schneier.com/books/applied-cryptography/)
- [Cryptography Engineering](https://www.schneier.com/books/cryptography-engineering/)
- [NIST Cryptographic Standards](https://csrc.nist.gov/projects/cryptographic-standards-and-guidelines)
- [RFC Cryptographic Protocols](https://tools.ietf.org/rfc/)

## 📈 Próximos Passos
- [ ] Implementar algoritmos pós-quânticos
- [ ] Adicionar benchmarks de performance
- [ ] Criar exemplos práticos de uso
- [ ] Implementar protocolos (TLS, SSH)
- [ ] Adicionar análise de side-channel
- [ ] Criar interface web educacional

## 🔗 Projetos Relacionados
- [JS Wallet Generator](../js-wallet-generator/) - Aplicação de criptografia Bitcoin
- [Solidity CoinLink Token](../solidity-coinlink-token/) - Criptografia em blockchain
- [Go Antifraud MS](../go-antifraud-ms/) - Aplicação de segurança

---

**Desenvolvido por:** Felipe Macedo  
**Contato:** contato.dev.macedo@gmail.com  
**GitHub:** [FelipeMacedo](https://github.com/felipemacedo1)  
**LinkedIn:** [felipemacedo1](https://linkedin.com/in/felipemacedo1)

> 💡 **Reflexão:** Este projeto proporcionou compreensão profunda dos fundamentos da criptografia moderna. A implementação prática de algoritmos complexos consolidou conhecimentos teóricos e demonstrou a importância da segurança em sistemas digitais.