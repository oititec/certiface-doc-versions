<p align="center">
 <img src="Documentation/Images/CertifaceHeader.png"/>
</p>

# Changelog

### [Versão 1.1.0](https://github.com/oititec/certiface-doc-versions/releases/tag/1.1.0)

Data: 18/11/2026

### Added
- Support hotfix and release branches in deployment workflow
- Paste button on credential screen and disable cnh digital for token flow
- Implementando saas inicialmente
- Spacing on screens
- Fix instructions e customs

### Changed
- `chore: update certiface SDK to 1.1.0`
- `chore: update certifaceSDKVersion to 1.1.0-snapshot`
- Subindo coverage do certiface doc
- Atualizando versão prd
- Atualizando conflito de packages
- Atualizando para lançamento em PRD
- Atualizando a base URL para teste
- Teste trocando a baseUrl
- Fix back button invisivel na permission screen
- Pequenos ajustes visuais
- Subindo versão para deploy

### Fixed
- Allow flow to continue when app key resolution fails
- Proguard rules for saas api and dagger factories
- ComposeBom version
- Ajuste device intelligence que estava quebrado
- Crash device Intelligence
- Icons invisible
- Layouts on some devices cutting edges

### [Versão 1.0.0](https://github.com/oititec/certiface-doc-versions/releases/tag/1.0.0)

Data: 30/03/2026

### Visão geral

- Substitui o SDK legado **Liveness 2D**: codebase **novo**, sem migração automática nem paridade de API com o legado.
- UI do fluxo em **Jetpack Compose** (Material 3).

---

### Integração (API pública)

| Etapa | Detalhe |
|--------|---------|
| Inicialização | `CertifaceDocSDK.initialize(context, config)` |
| Execução do fluxo | `CertifaceDocManager.start(config, callback)` |
| Config | `createSDKConfig(...)` → `CertifaceDocConfig` |

**`CertifaceDocConfig`**

| Campo | Descrição |
|--------|-----------|
| `appKey` | Credencial para inicio da sessão |
| `environment` | `HML` ou `PRD` (Ambientes). |
| `theme` | Opcional; `null` usa o tema padrão do SDK. |
| `enableCnhDigital` | Habilita o fluxo de CNH digital. |
| `enablePdfUpload` | Habilita envio de documento em PDF. |

---

### Customização

- **`CertifaceDocTheme.build { }`** — DSL para tema: instruções, permissão, captura, loading, QR, uploads (documento / CNH digital), resultado, instruções complementares, fontes por papel de texto.
- **Granular** — ajuste de cores, textos e recursos por etapa.
- **`setCustomScreens`** — substituição **completa** de telas por Composables próprios, quando a UI precisa ser 100% sob controle do integrador.

---

### Requisitos

- Android **minSdk 26** · **compileSdk 36** · **Kotlin 2.0.x** · **Java 17**

---

### Dependência Gradle

- Dependência: artefato **`manager`** (`br.com.certiface:manager:1.0.0`). 
