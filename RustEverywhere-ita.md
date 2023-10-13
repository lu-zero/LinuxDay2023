# Rust: OVUNQUE

## LinuxDay Torino 2023

### Luca Barbato
 - <lu_zero@gentoo.org>
 - <lu_zero@videolan.org>

---
# Intro

## Chi sono io?
* Sviluppo Gentoo, una distribuzione Linux molto flessibile e duttile.
* Contribuisco a diversi progetti sotto l'ombrellone VideoLan
* Ultimamente contribuisco a Rust e scrivo software multimediale in questo linguaggio
  - [rav1e](https://github.com/xiph/rav1e/) ad esempio.
* E per non farmi mancare nulla lo uso pure in ambito IoT implementando [Web Of Things](https://github.com/wot-rust).

---
### Ringraziamenti

Pietro Albini, Edoardo Morandi e tutti i partecipanti del [meetup torinese](https://t.me/torinorust) e del [meetup italiano](https://t.me/rustlang_it).

---
# Intro

## Chi siete voi?
* Chi ha sentito parlare di Rust?
* Quanti di voi programmano in Rust?

---
# Intro

## Rust in poche parole
> Un linguaggio che permette a chiunque di sviluppare software affidabile ed efficiente.
> [rust-lang.org](https://www.rust-lang.org/it/)

### Punti chiave
* È un linguaggio per **tutti**.
* Per scrivere programmi **efficienti**.
  * ed **affidabili**

---
# Intro

## Rust in altre parole (e con meno marketing)

* È un linguaggio di programmazione di sistema che offre garanzie forti sul comportamento del codice scritto
  * Il compilatore evita una serie di tipi di errori **molto** comuni.
  * Il compilatore è in grado di ottimizzare meglio il codice prodotto come **effetto collaterale** dell'avere maggiori informazioni.
  * Scrivere codice molto **complicato** (and esempio **multi-thread** o asincrono) diventa di conseguenza più **semplice**.
* È un linguaggio in cui **ergonomia** e documentazione non sono questioni secondarie.
* È un linguaggio che **costringe** ad essere consci di quello che si fa.
  * Il compilatore ti tiene **per mano** e spesso ti guida.

---
# Intro

Questo l'avevo già detto nel 2019, ed apparentemente in questi 4 anni molti si sono convinti della sua bontà.

* Rust possiamo dire che se non è assolutamente __OVUNQUE__, decisamente lo troviamo in un sacco di posti.

---
## Rust nei browser

### Mozilla aveva dato il LA
> "The style component is the part of a browser that applies CSS rules to a page. This is a top-down process on the DOM tree: given the parent style, the styles of children can be calculated independently: a perfect use-case for parallel computation. By 2017, Mozilla had made two previous attempts to parallelize the style system using C++. Both had failed"
> [Mozilla](https://hacks.mozilla.org/2019/02/rewriting-a-browser-component-in-rust/)


---
## Rust nei browser

### E Google non è da meno ormai
> "We are pleased to announce that moving forward, the Chromium project is going to support the use of third-party Rust libraries from C++ in Chromium. To do so, we are now actively pursuing adding a production Rust toolchain to our build system. This will enable us to include Rust code in the Chrome binary within the next year. We’re starting slow and setting clear expectations on what libraries we will consider once we’re ready."
> [Google Security Blog](https://security.googleblog.com/2023/01/supporting-use-of-rust-in-chromium.html)


---
## Rust nei browser

### E apparentemente anche la Linux Foundation pensa che sia una buona idea
> The Linux Foundation, the nonprofit organization enabling mass innovation through open source, today announced it will host the Servo web engine. Servo is an open source, high-performance browser engine designed for both application and embedded use and is written in the Rust programming language, bringing lightning-fast performance and memory safety to browser internals. Industry support for this move is coming from Futurewei, Let’s Encrypt, Mozilla, Samsung, and Three.js, among others.
[Linux Foundation Press Release](https://www.linuxfoundation.org/press/press-release/open-source-web-engine-servo-to-be-hosted-at-linux-foundation)

> The independent, modular, and embeddable web rendering engine written in Rust to nurture a stronger European open source ecosystem
[Linus Foundation Europe Newsroom](https://linuxfoundation.eu/newsroom/servo-web-rendering-engine-joins-linux-foundation-europe)


---
## Rust nel cellulare?

### Se usi Android decisamente sì
* Alcuni componenti delle versioni recenti di Android sono scritte in rust, sono partiti da una reimplementazione dello stack bluetooth che ancora troviamo [qui](https://android.googlesource.com/platform/system/bt/+/refs/heads/main).
* Ed come da tradizione han finito per inventare modi creativi per farsi male con i [build system](https://security.googleblog.com/2021/05/integrating-rust-into-android-open.html).
* Ora c'è addirittura ha un mini-corso su come [usarlo su android](https://google.github.io/comprehensive-rust/android.html)
    * ed è uno dei linguaggi supportati da [Android Studio](https://source.android.com/docs/setup/build/rust/building-rust-modules/overview).

---
## Rust nel cellulare?

### E su iOS?
* Dato che Apple ha abbracciato Swift, non c'è (ancora) un ottimo supporto ufficiale
    * Ma terze parti rendono facile usarlo.
        * Ad esempio [tauri](https://github.com/tauri-apps/cargo-mobile2).


---
## Rust sul desktop?

### Microsoft adora Rust
> "As we’ve seen, roughly 70% of the security issues that the MSRC assigns a CVE to are memory safety issues. This means that if that software had been written in Rust, 70% of these security issues would most likely have been eliminated."
> [Microsoft](https://msrc-blog.microsoft.com/2019/07/22/why-rust-for-safe-systems-programming/)

* Quindi ora sta [riscrivendo](https://www.theregister.com/2023/04/27/microsoft_windows_rust/) parti di Windows in Rust.
* E contribuendo crate per scrivere sia [applicazioni](https://github.com/microsoft/windows-rs) sia [driver](https://github.com/microsoft/windows-drivers-rs).

---
## Rust sul desktop?

### Ma è il LinuxDay!
* Anche per Linux abbiamo desktop scritti in Rust
    * [COSMIC](https://github.com/pop-os/cosmic) di [`Pop!_OS`](https://github.com/pop-os) sta venendo riscritto in Rust.
    * [smithay](https://github.com/Smithay/smithay) è una buona implementazione di Wayland, non dissimile a [wlroots](https://gitlab.freedesktop.org/wlroots/wlroots/)
    * [jay](https://github.com/mahkoh/jay) è impressionante ma concettualmente agli antipodi

---
## Rust sul desktop?

### Ma è il LinuxDay!
- E moltissime librerie scritte (o riscritte) in Rust stanno pian piano facendosi strada
    * [librsvg](https://gitlab.gnome.org/GNOME/librsvg) è stata un apripista
    * [rustybuzz](https://github.com/RazrFalcon/rustybuzz) ha una situazione un po' più [travagliata](https://github.com/RazrFalcon/rustybuzz/issues/74#issuecomment-1728593933).
    * E ve ne sono molte altre.

---
## Rust dentro i kernel

### Se Rust è così buono vogliam lasciare solo Microsoft a giocarci?
* Da Linux 6.1 c'è un parziale supporto di Rust che via via cresce
    * E ci sono già driver notevoli scritti in Rust, ad esempio quello per la GPU dell'M1.
* FreeBSD [sperimenta](https://github.com/johalun/rustkpi/tree/master/rust/kmod-e1000) [anche](https://research.nccgroup.com/2022/08/31/writing-freebsd-kernel-modules-in-rust/) lui.
* Ed esiste [Redox](https://redox-os.org) se qualcuno vuole un intero sistema operativo scritto in partenza in Rust.


---
## Rust nel tostapane

### Rust ed IoT
- Rust grazie a [`no_std`](https://docs.rust-embedded.org/book/intro/no-std.html) parte in vantaggio
    * E l'approccio di avere la liberia standard "spegnibile" permette di graduare cosa si supporta
        * `std` per avere tutta la libreria standard.
        * `core` per avere solo le componenti che non devono allocare.
        * `alloc` per avere anche le parti di std che allocano.
    * Moltissimi crate nascono per funzionare anche su bare metal.
---
## Rust nel tostapane

### Rust ed IoT
- [expressif](https://www.espressif.com/en/news/ESP_RUST_training) ha abbracciato Rust per le sue architetture esp32.
    * in particolare la sua versione a base di RISC-V permette di fare [moltisismo](https://github.com/ivmarkov/rust-esp32-std-demo).
* [embassy](https://embassy.dev/) supporta molteplici sistemi, inclusi STM32 e nRF* oltre a esp32 in ogni sua forma o quasi.
* Esistono diverse `HAL` per molteplici archietture su cui poter scrivere il proprio sistema senza partire da zero.

---
## Rust nelle Automobili?

* Grazie a [Ferrous System](https://ferrous-systems.com) è ora possibile usare Rust in ambito automotive ed industriale
    * Han faticato molto ma ora esistono compilatori Rust che supportano `ISO 26262 ASIL-D` and `IEC 61508 SiL4`.
    * E se quanto stan facendo assieme all [ESA](https://ferrous-systems.com/blog/rust-for-mission-critical-applications/) porta i suoi frutti...
        * Rust su Marte?

---
# Conclusione

Sono ben 4 anni che parlo di Rust al LinuxDay:
* Nel **2017** ho raccontato Rust, spiegando perchè **non** lo si dovesse usare per riscrivere il mondo.
* Nel **2018** ho illustrato come mai Rust sia stato scelto per scrivere [rav1e](https://github.com/xiph/rav1e/).
* Nel **2019** vi ho raccontato perchè le ragioni per non usarlo eran poche.
* **Oggi** vi ho raccontato in quanti posti potete trovarlo ed in quanti altri posti lo troveremo in futuro.

---
# Domande?


---
# Riferimenti

- [https://github.com/rust-torino](https://github.com/rust-torino)
- [https://github.com/lu-zero/linuxday2023](https://github.com/lu-zero/linuxday2023)
- [https://www.rust-lang.org/it/](https://www.rust-lang.org/it/)
- Twitter: [@lu\_zero\_](https://twitter.com/lu_zero_)
