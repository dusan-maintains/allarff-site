# allarff.com — публикация (GitHub Pages)

## Файлы
- `index.html` — одностраничник oss-health-scan (факты сверены с README; фичи 1.7.0 — blast radius и git-ref diff — спрятаны в HTML-комментарий до публикации 1.7.0 на npm, потом раскомментировать).
- `CNAME` — `allarff.com` (в корне репо).

## Шаги
1. Создай отдельный репо `allarff-site` (public), закинь оба файла в корень.
2. Settings → Pages → Source: main / root. Custom domain: `allarff.com` → Save (сначала домен в Pages, потом DNS).
3. DNS у регистратора (замени парковку):
   - 4× A-записи для `@`: 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153
   - CNAME `www` → `dusan-maintains.github.io`
4. Дождись сертификата → включи **Enforce HTTPS**.

## Почта hunter.dusan@allarff.com (ОБЯЗАТЕЛЬНО для заявки)
Домен сейчас смотрит на чужой MX (businessidentity.llc) — письма не доходят. Верни DNS под Cloudflare и включи Email Routing:
- MX: `route1.mx.cloudflare.net`, `route2.mx.cloudflare.net`, `route3.mx.cloudflare.net`
- SPF TXT: `v=spf1 include:_spf.mx.cloudflare.net ~all`
- Routing → forward `hunter.dusan@allarff.com` → свой gmail.
Это же воскресит cfmail-канал фермы.

## Проверка перед подачей
- [ ] https://allarff.com открывает страницу (не парковку)
- [ ] письмо с gmail на hunter.dusan@allarff.com доходит
- [ ] npm показывает 1.7.0 → тогда раскомментировать 2 фичи в index.html
