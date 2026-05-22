# Deploy Rehberi (Basınç/Hacim Muayene Hesaplayıcı)

Bu proje statik HTML olduğu için en hızlı yöntem **GitHub Pages** veya **Netlify** ile yayınlamaktır.

## 1) GitHub Pages ile deploy

1. Değişikliklerin commit edildiğini kontrol edin:
   ```bash
   git status
   ```
2. Uzak repo bağlantısını doğrulayın:
   ```bash
   git remote -v
   ```
3. Branch'i gönderin:
   ```bash
   git push origin work
   ```
   > Eğer varsayılan branch `main` ise:
   > ```bash
   > git push origin main
   > ```
4. GitHub'da ilgili repoda:
   - **Settings → Pages**
   - **Build and deployment / Source**: `Deploy from a branch`
   - Branch: `work` (veya `main`), Folder: `/ (root)`
5. 1-2 dakika sonra URL açılır:
   - `https://<kullanici>.github.io/<repo>/`

## 2) Netlify ile deploy

1. Netlify'da **Add new site → Import an existing project**.
2. GitHub reponuzu seçin.
3. Build ayarları:
   - Build command: **boş bırakın**
   - Publish directory: `/` veya boş (root)
4. Deploy edin.

## 3) Sık karşılaşılan deploy hataları

- `Updates were rejected`:
  ```bash
  git pull --rebase origin work
  git push origin work
  ```
- Yanlış branch'e push:
  ```bash
  git branch --show-current
  ```
- Pages açık ama 404:
  - `index.html` repo kökünde olmalı (bu projede kökte).
  - Pages branch/folder ayarı doğru olmalı.
- Cache sorunu:
  - Tarayıcıyı hard refresh yapın (`Ctrl+F5`).

## 4) Hızlı kontrol listesi

```bash
git status
git branch --show-current
git remote -v
git push origin <branch>
```

Deploy sonrası test:
- Ana sayfa (`index.html`) açılıyor mu?
- `Basınç` ve `Hacim` sayfalarına yönlendirme çalışıyor mu?
- Hesapla butonları sonuç üretiyor mu?
