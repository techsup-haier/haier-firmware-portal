# Haier Brasil — Firmware Center

Portal interno para busca e download de firmwares de Smart TVs Haier.

## 🚀 Deploy (GitHub Pages)

### 1. Criar o repositório
1. Acesse [github.com/new](https://github.com/new)
2. Nome: `haier-firmware-portal`
3. Visibilidade: **Public** (necessário para GitHub Pages gratuito)
4. Crie o repositório e faça upload dos 3 arquivos (`index.html`, `firmware-catalog.json`, `README.md`)

### 2. Ativar GitHub Pages
1. No repositório, vá em **Settings → Pages**
2. Em "Source", selecione **Deploy from a branch**
3. Branch: `main`, pasta: `/ (root)`
4. Clique **Save**
5. Em ~2 minutos, o site estará disponível em:
   `https://SEU-USUARIO.github.io/haier-firmware-portal/`

### 3. Subir os firmwares como Release Assets
Para cada firmware:
1. No repositório, vá em **Releases → Create a new release**
2. Tag: `fw-MODELO` (ex: `fw-H50K6UG`)
3. Título: `Firmware H50K6UG`
4. Arraste o arquivo .zip do firmware para a área de upload
5. Clique **Publish release**
6. Copie o URL do asset (clique com botão direito no link do arquivo → Copiar link)

### 4. Atualizar o `firmware-catalog.json`
Substitua as URLs de exemplo pelas URLs reais dos release assets:
```json
{
  "model": "H50K6UG",
  "description": "Smart TV 50\" 4K UHD",
  "file": "H50K6UG_update.zip",
  "size": "1.6 GB",
  "date": "2026-07-15",
  "url": "https://github.com/SEU-USUARIO/haier-firmware-portal/releases/download/fw-H50K6UG/H50K6UG_update.zip"
}
```

---

## 🔄 Manutenção: Atualizar um firmware

1. Vá em **Releases** no repositório
2. Encontre a release do modelo (ex: `fw-H50K6UG`)
3. Clique em **Edit** (ícone de lápis)
4. Delete o arquivo antigo e arraste o novo
5. Salve
6. Edite o `firmware-catalog.json` → atualize `date`, `size` e `file` se necessário
7. Commit → o site atualiza automaticamente

## 🔄 Manutenção: Adicionar um modelo novo

1. Crie uma nova **Release** com a tag `fw-NOVOMODELO`
2. Anexe o arquivo de firmware
3. Edite o `firmware-catalog.json` e adicione um novo objeto ao array
4. Commit → pronto

---

## 📁 Estrutura

```
haier-firmware-portal/
├── index.html              ← Site completo (HTML + CSS + JS)
├── firmware-catalog.json   ← Catálogo de modelos e links
└── README.md               ← Este arquivo
```

## ⚙️ Stack

| Camada | Tecnologia | Custo |
|--------|-----------|-------|
| Frontend | HTML/CSS/JS puro | R$ 0 |
| Hospedagem | GitHub Pages | R$ 0 |
| Armazenamento | GitHub Releases | R$ 0 |
| "Banco de dados" | JSON estático | R$ 0 |
| **Total** | | **R$ 0/mês** |
