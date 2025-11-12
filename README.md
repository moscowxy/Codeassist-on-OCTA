#  OCTA üzerinde CodeAssist 

## 0) Sudo'yu Yükle

```bash
apt install -y sudo
```

## 1) Sistemi Güncelleyin

```bash
sudo apt update && sudo apt upgrade -y
```

## 2) Python 3.10+ Kontrolü

```bash
python3 --version
```

Python 3.10 veya üzeri değilse:

```bash
sudo apt install -y python3 python3-venv python3-pip
```

## 3) Docker Kurulumu

```bash
sudo apt install -y docker.io
sudo systemctl enable --now docker
sudo usermod -aG docker "$USER"
```

## 4) UV (Astral) Kurulumu

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
export PATH="$HOME/.local/bin:$PATH"
```

## 5) CodeAssist Deposunu Klonlayın

```bash
git clone https://github.com/xailong-6969/codeassist
cd codeassist
```

## 6) Hugging Face Token Oluşturun

[https://huggingface.co](https://huggingface.co) → Access Token → Write izinli.

## 7) CodeAssist’i Çalıştırın

```bash
uv run run.py
```

## 8) Yeni bir Ekran Arayüzü Açma (Sağ Tık + H)

CodeAssist çalıştıktan sonra:
Mouse sağ tık + **H**

## 9) Cloudflared Kurulumu

```bash
sudo apt-get install -y wget
wget https://github.com/cloudflare/cloudflared/releases/latest/download/cloudflared-linux-amd64.deb
sudo dpkg -i cloudflared-linux-amd64.deb
```

### Tüneli Açın

```bash
cloudflared tunnel --url http://localhost:3000
```

---
