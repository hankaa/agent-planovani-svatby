# Svatební agent 💍

Znovupoužitelný **asistent pro přípravu svatby** pro Claude. Vznikl destilací jedné reálné svatby — všechna konkrétní jména, ceny a kontakty jsou pryč, zůstala struktura, postupy a nasbírané zkušenosti.

Repo se dá použít **dvěma způsoby** (a klidně oběma najednou).

---

## 1) Stáhnout a používat jako svůj projekt (nejjednodušší)

Pro pár, který chce hned začít a nic neinstalovat.

1. Stáhni repo (ZIP nebo `git clone`).
2. Otevři složku v Claudovi (Cowork / Claude Code) jako pracovní složku.
3. Soubor `CLAUDE.md` agentovi sám řekne, jak se má chovat. Projdi `MASTER-CHECKLIST.md`, kde jsi, a začni mu předávat podklady.

Jak ti chodí e-maily od dodavatelů a zprávy od hostů, agent je ukládá do `RAW/`, vytahuje důležité do přehledů a aktualizuje `TODO.md`. Když chceš vědět „co teď", koukni do `TODO.md`. Když začínáš novou oblast, koukni do `PLAYBOOK.md`.

## 2) Nainstalovat jako plugin/skill (znovupoužitelné napříč projekty)

Pro toho, kdo chce „svatební režim" zapnout kdekoli a nechat si od skillu **založit čerstvou strukturu projektu**.

```shell
/plugin marketplace add <git-url-tohoto-repa>
/plugin install svatebni-planovac@svatebni-agent
```

Pak stačí říct, že plánuješ svatbu — skill se přihlásí, nabídne založení projektu a dál se chová podle stejných pravidel. Aktualizace: majitel repa pushne commit, ty si dáš `/plugin marketplace update`.

> Pozn.: nainstalovaný plugin se kopíruje do cache a nesmí sahat mimo svou složku, proto má skill vlastní kopii šablony v `plugins/svatebni-planovac/skills/svatebni-planovac/assets/template/`.

---

## Co je kde

| Soubor / složka | K čemu |
|---|---|
| `CLAUDE.md` | Instrukce pro agenta (chování, pravidla, naučené vzorce). |
| `MASTER-CHECKLIST.md` | Časová osa úkolů 12+ měsíců → po svatbě. |
| `PLAYBOOK.md` | Co s kým probrat u každé oblasti + záludnosti z praxe. |
| `TODO.md` | Centrální přehled úkolů. Zdroj pravdy. |
| `Dodavatele/` | Přehledy dodavatelů (`prehled.md`). |
| `Svatebni-web/` | Příprava webu + šablona RSVP formuláře. |
| `Hoste/` | Požadavky hostů a pomocníci. |
| `Koordinace/` | Role na svatební den. |
| `Hry/`, `Tisk.md`, `Co-vzit-s-sebou.md`, `Last-minute-zmeny.md` | Hry, tisk, balení, změny na poslední chvíli. |
| `RAW/` | Archiv surových podkladů. |
| `.claude-plugin/marketplace.json` | Katalog marketplace (pro instalaci). |
| `plugins/svatebni-planovac/` | Plugin se skillem + nabundlovaná šablona. |

## Filozofie

Jeden zdroj pravdy (`TODO.md`). Surové vs. zpracované (`RAW/` → přehledy). Nic nezapadne (úkol → hned do TODO). Pár rozhoduje, agent připravuje.

## Použití a sdílení

Šablona je anonymizovaná a určená k volnému použití a úpravám. Vezmi ji, naplň vlastními daty a uprav si pravidla v `CLAUDE.md` podle sebe.
