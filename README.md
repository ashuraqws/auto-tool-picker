# auto-tool-picker

Claude Code için bir skill. Kurulu MCP sunucuları, skill'ler ve eklentiler arasından işe en uygun olanı seçip kendisi kullanır. Kullanıcının araç adı yazmasına gerek kalmaz.

## Kurulum (30 saniye)

Claude Code içinde iki komut yazın:

```
/plugin marketplace add ashuraqws/auto-tool-picker
/plugin install auto-tool-picker
```

Kurulumdan sonra Claude Code'u yeniden açın. Kontrol: `/auto-tool-picker` yazın, skill listede görünmeli.

### Elle kurulum (eklenti sistemi olmadan)

1. Repoyu klonlayın: `git clone https://github.com/ashuraqws/auto-tool-picker`
2. `SKILL.md` dosyasını şu klasöre koyun: `C:\Users\<kullanıcı>\.claude\skills\auto-tool-picker\`
3. Claude Code'u kapatıp yeniden açın.

Sadece tek bir proje için kullanmak isterseniz klasörü projenin `.claude\skills\` klasörüne koyun.

## Kullanım

Normal bir istek yazın. Skill otomatik tetiklenir.

- Örnek: "Bu repodaki açık PR'ları listele"
- Doğrudan çağırmak için: `/auto-tool-picker <istek>`

Okuma işlemleri sormadan yapılır. Gönderme, silme veya dış kayıt değiştirme gibi işlerde önce onay ister.

## Sınırlar

- Yalnızca zaten kurulu ve açık olan araçları kullanır. Yeni araç kurmaz, açmaz, ayarlamaz.
- Hangi aracı seçeceği Claude'un yorumuna bağlıdır, garanti değildir.
- Testler `evals/evals.json` içinde. Gerçek sonuçlar henüz ölçülmedi.

## Dosyalar

- `.claude-plugin/`: eklenti ve marketplace tanımı.
- `skills/auto-tool-picker/SKILL.md`: eklentinin kullandığı skill.
- `SKILL.md`: elle kurulum için aynı skill'in kopyası. İkisi aynı tutulmalı.
- `evals/evals.json`: test senaryoları.
