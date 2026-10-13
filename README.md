# auto-tool-picker

Claude Code için bir skill. Kurulu MCP sunucuları, skill'ler ve eklentiler arasından işe en uygun olanı seçip kendisi kullanır. Kullanıcının araç adı yazmasına gerek kalmaz.

## Kurulum

Skill, Claude Code'un kişisel skill klasörüne konur:

```
C:\Users\<kullanıcı>\.claude\skills\auto-tool-picker\SKILL.md
```

Adımlar:

1. Bu repoyu indirin veya klonlayın.
2. `auto-tool-picker` klasörünü şu konuma kopyalayın: `C:\Users\<kullanıcı>\.claude\skills\`
3. Claude Code'u kapatıp yeniden açın.
4. Kontrol: Claude Code içinde `/auto-tool-picker` yazın, skill listede görünmeli.

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

- `SKILL.md`: skill'in kendisi.
- `evals/evals.json`: test senaryoları.
