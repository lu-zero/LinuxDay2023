---
footer: '![height:1em](assets/Luminem2020.svg) ![height:1em](assets/rust-italia.svg) ![height:1em](assets/rust-torino.svg) LinuxDay Torino 2023 - Rust: OVUNQUE '
---



# <!--fit--> Rust: OVUNQUE
![bg right fit](assets/ferris-left.svg)

## LinuxDay Torino 2023

### Luca Barbato
 - <lu_zero@gentoo.org>
 - <lu_zero@videolan.org>

---
# <!--fit--> Intro

---
<!-- header: Intro -->

## <!--fit--> Chi sono io?
* Sviluppo Gentoo, una distribuzione Linux molto flessibile e duttile.
* Contribuisco a diversi progetti sotto l'ombrellone VideoLan
* Contribuisco a Rust e scrivo software multimediale in questo linguaggio
  - [rav1e](https://github.com/xiph/rav1e/) ad esempio.
* E per non farmi mancare nulla lo uso pure in ambito IoT implementando [Web Of Things](https://github.com/wot-rust).

---
## <!--fit--> Chi siete voi?
* Chi ha sentito parlare di Rust?
* Quanti di voi programmano in Rust?

---
## <!--fit--> Rust in poche parole
> Un linguaggio che permette a chiunque di sviluppare software affidabile ed efficiente.
> [rust-lang.org](https://www.rust-lang.org/it/)

### Punti chiave
* È un linguaggio per **tutti**.
* Per scrivere programmi **efficienti**.
  * ed **affidabili**

---
## <!--fit--> Rust in altre parole

* È un linguaggio di programmazione di sistema che offre garanzie forti sul comportamento del codice scritto
  * Il compilatore evita una serie di tipi di errori **molto** comuni.
  * Scrivere codice molto **complicato** (and esempio **multi-thread** o asincrono) diventa di conseguenza più **semplice**.
* È un linguaggio in cui **ergonomia** e documentazione non sono questioni secondarie.

---
## <!--fit--> Rust in altre parole

* È un linguaggio che **costringe** ad essere consci di quello che si fa.
  * Il compilatore ti tiene **per mano** e spesso ti guida.
  * Quando il compilatore non può stabilire la correttezza del codice è necessario marcarlo di conseguenza con `unsafe`
* Il compilatore è in grado di ottimizzare meglio il codice prodotto come **effetto collaterale** dell'avere maggiori informazioni.

---
Questo l'avevo già detto nel 2019, ed apparentemente in questi 4 anni molti si sono convinti della sua bontà.

* Ora lo possiamo trovare in un sacco di posti ed usato da moltissime persone ed organizzazioni.


---
# <!--fit--> Ovunque?
* Rust possiamo dire che se non è assolutamente __OVUNQUE__, decisamente lo troviamo in un sacco di posti.

---
<!-- header: Ovunque? -->

## <!--fit-->Pensiamo al software con cui interagiamo

* Browser
* Cellulare
* Desktop
* Server
* Tostapane

---
# <!--fit--> Nei browser?

---
<!-- header: Ovunque? Nel tuo browser! -->
## I browser sono fra i software più usati

* E fra i software più complessi
    * E fra i più sfruttati per far danni
* Ha perfettamente senso evitare a priori problemi quando li si scrivere

---
### Mozilla aveva dato il LA
> "The style component is the part of a browser that applies CSS rules to a page. This is a top-down process on the DOM tree: given the parent style, the styles of children can be calculated independently: a perfect use-case for parallel computation. By 2017, Mozilla had made two previous attempts to parallelize the style system using C++. Both had failed"
> [Mozilla](https://hacks.mozilla.org/2019/02/rewriting-a-browser-component-in-rust/)


---
### E Google non è da meno ormai
> "We are pleased to announce that moving forward, the Chromium project is going to support the use of third-party Rust libraries from C++ in Chromium. To do so, we are now actively pursuing adding a production Rust toolchain to our build system. This will enable us to include Rust code in the Chrome binary within the next year. We’re starting slow and setting clear expectations on what libraries we will consider once we’re ready."
> [Google Security Blog](https://security.googleblog.com/2023/01/supporting-use-of-rust-in-chromium.html)


---
### E apparentemente anche la Linux Foundation pensa che sia una buona idea
> The Linux Foundation, the nonprofit organization enabling mass innovation through open source, today announced it will host the Servo web engine. Servo is an open source, high-performance browser engine designed for both application and embedded use and is written in the Rust programming language, bringing lightning-fast performance and memory safety to browser internals. Industry support for this move is coming from Futurewei, Let’s Encrypt, Mozilla, Samsung, and Three.js, among others.
[Linux Foundation Press Release](https://www.linuxfoundation.org/press/press-release/open-source-web-engine-servo-to-be-hosted-at-linux-foundation)

> The independent, modular, and embeddable web rendering engine written in Rust to nurture a stronger European open source ecosystem
[Linux Foundation Europe Newsroom](https://linuxfoundation.eu/newsroom/servo-web-rendering-engine-joins-linux-foundation-europe)


---
<!-- header: Ovunque? Nel tuo cellulare! -->
# <!--fit--> Nel cellulare?


---
### <!--fit-->Se usi Android decisamente sì
* Alcuni componenti delle versioni recenti di Android sono scritte in rust, sono partiti da una reimplementazione dello stack bluetooth che ancora troviamo [qui](https://android.googlesource.com/platform/system/bt/+/refs/heads/main).
* E come da tradizione han finito per inventare modi creativi per farsi male con i [build system](https://security.googleblog.com/2021/05/integrating-rust-into-android-open.html).
* Ora c'è addirittura ha un mini-corso su come [usarlo su android](https://google.github.io/comprehensive-rust/android.html)
    * ed è uno dei linguaggi supportati da [Android Studio](https://source.android.com/docs/setup/build/rust/building-rust-modules/overview).

---
### <!--fit--> E su iOS?
* Dato che Apple ha abbracciato Swift, non c'è (ancora) un ottimo supporto ufficiale
    * Ma terze parti rendono facile usarlo.
        * Ad esempio [tauri](https://github.com/tauri-apps/cargo-mobile2).


---
<!-- header: Ovunque? Nel tuo desktop! -->
# <!--fit--> Sul desktop?

---
### Microsoft adora Rust
> "As we’ve seen, roughly 70% of the security issues that the MSRC assigns a CVE to are memory safety issues. This means that if that software had been written in Rust, 70% of these security issues would most likely have been eliminated."
> [Microsoft](https://msrc-blog.microsoft.com/2019/07/22/why-rust-for-safe-systems-programming/)

* Quindi ora sta [riscrivendo](https://www.theregister.com/2023/04/27/microsoft_windows_rust/) parti di Windows in Rust.
* E contribuendo crate per scrivere sia [applicazioni](https://github.com/microsoft/windows-rs) sia [driver](https://github.com/microsoft/windows-drivers-rs).

---
### <!--fit--> Ma è il LinuxDay!
* Anche per **Linux** abbiamo desktop scritti in Rust
    * [COSMIC](https://github.com/pop-os/cosmic) di [`Pop!_OS`](https://github.com/pop-os) sta venendo riscritto in Rust.
    * [smithay](https://github.com/Smithay/smithay) è una buona implementazione di Wayland
        * non dissimile a [wlroots](https://gitlab.freedesktop.org/wlroots/wlroots/) come spirito.
    * [jay](https://github.com/mahkoh/jay) è ormai impressionante e segue la filosofia opposta.

---
### <!--fit--> Terminali
* [alacritty](https://alacritty.org/) è stato fra i primi, spartano ma potente ed embeddabile.
* [rio](https://raphamorim.io/rio/) è più amichevole come UI
    * anch'esso dimostra come sia facile scrivere software gpu-accelerato.
* [wezterm](https://wezfurlong.org/wezterm) è ancora più completo e rimane nello stesso filone.

---
### <!--fit--> Command line utility
* [ripgrep](https://crates.io/crates/ripgrep) è un grep più veloce ed amichevole.
* [bat](https://crates.io/crates/bat) è un cat con syntax highlighting e molto altro.
* [gitoxide](https://crates.io/crates/gitoxide) è una reimplementazione di Git.
* [uutils](https://github.com/uutils) fornisce una reimplementazione di [coreutils](https://github.com/uutils/coreutils) e [findutils](https://github.com/uutils/findutils).
* [bottom](https://crates.io/crates/bottom) è una valida alternativa ad [htop](https://github.com/htop-dev/htop/).

---
### <!--fit-->Applicazioni Grafiche

* [lapce](https://lapce.dev) mira ad essere un valido sostituto di Code.
* [graphite](https://graphite.rs) è un editor grafico scritto in rust e che si può usare dal browser.
* [servo](https://servo.org) è un browser web in sviluppo.
* [veloren](https://veloren.net) è un RPG cubettoso simile a Minecraft per certi versi.

---
### <!--fit--> Librerie
* Riscrivere tutto in Rust, buttando via tutto in un colpo solo non ha sempre senso
    * Spesso è meglio usare un approccio incrementale
* Ecco perchè abbiamo Rust assieme ad altri linguaggi e librerie con parti di Rust.

---
### <!--fit--> Librerie con parti di Rust
* [librsvg](https://gitlab.gnome.org/GNOME/librsvg) è stata un apripista
* [gstreamer](https://gitlab.freedesktop.org/gstreamer/gst-plugins-rs) ha molti nuovi plugin scritti in rust.
* [libcurl](https://daniel.haxx.se/blog/2022/02/01/curl-with-rust/) ora ha backend per [hyper](https://crates.io/crates/hyper), [rustls](https://crates.io/crates/rustls) e [quiche](https://crates.io/crates/quiche).
* [cryptography](https://pypi.org/project/cryptography) implementa alcuni cifrari in Rust.

---
### <!--fit--> Librerie nate in Rust (Data Science)

* [polars](pola.rs) è una valida alternativa al famoso [pandas](https://pandas.pydata.org).
* [ndarray](https://github.com/rust-ndarray) risolve gli stessi problemi che `numpy.ndarray` risolve in Python.
    * Con tanto di [guida](https://docs.rs/ndarray/latest/ndarray/doc/ndarray_for_numpy_users/) alla conversione.
* [evcxr](https://github.com/evcxr/evcxr) Permette di integrare Rust dentro [Jupyter](https://jupyter.org/).
* [poloto](https://crates.io/crates/poloto) e [plotters](https://github.com/plotters-rs/plotters) per visualizzare i dati.

---
### <!--fit--> Librerie nate in Rust (Machine Learning)

* [burn](https://github.com/burn-rs/burn) mira ad essere una soluzione completa per construire allenare ed eseguire reti neurali.
    * Supporta differenti backend, da `ndarray` per girare ovunque ci sia una cpu a `wgpu` per sfruttare hardware grafico.
* [candle](https://github.com/huggingface/candle) è un approccio più minimalista simile a PyTorch.
    * Arriva con implementazioni di [whisper](https://huggingface.co/spaces/lmz/candle-whisper), [LLaMA2](https://huggingface.co/spaces/lmz/candle-llama2), [T5](https://huggingface.co/spaces/radames/Candle-T5-Generation-Wasm), [yolo](https://huggingface.co/spaces/lmz/candle-yolo), [Segment Anything](https://huggingface.co/spaces/radames/candle-segment-anything-wasm).
    * E come molti altri crate, lo si può usare anche nel browser e in generale da altri linguaggi

---
### <!--fit--> Crate rust sotto mentite spoglie
* Crate che si fingono pacchetti python:
    * [polars](https://crates.io/crates/polars), una alternativa a `pandas`
    * [deltalake](https://crates.io/crates/deltalake), per accedere a data lake di `delta.io`
    * [candle](https://github.com/huggingface/candle), così migrare da PyTorch diventa ancora più indolore.
* Crate che si fingono librerie C:
    * [rav1e](https://crates.io/crates/rav1e), un encoder AV1.
    * [rustls-ffi](https://github.com/rustls/rustls-ffi), una implementazione di TLS
    * [libimagequant](https://github.com/ImageOptim/libimagequant), una libreria per ottimizzare PNG e GIF.
    * [pkgcraft](https://github.com/pkgcraft), una reimplementazione di Portage in rust.

---
<!-- header: Ovunque? Nei server! -->
# <!--fit--> E sul server?

---
### <!--fit--> Se Rust è così buono vogliam lasciare solo Microsoft a giocarci?
* Da Linux 6.1 c'è un parziale supporto di Rust che via via cresce
    * E ci sono già driver notevoli scritti in Rust, ad esempio quello per la [GPU dell'M1](https://github.com/AsahiLinux/linux/tree/asahi/drivers/gpu/drm/asahi).
* FreeBSD [sperimenta](https://github.com/johalun/rustkpi/tree/master/rust/kmod-e1000) [anche](https://research.nccgroup.com/2022/08/31/writing-freebsd-kernel-modules-in-rust/) lui.
* Ed esiste [Redox](https://redox-os.org) se qualcuno vuole un intero sistema operativo scritto in Rust sin dall'inizio.

---
### <!--fit--> Application Server Web

* [rocket](https://github.com/SergioBenitez/Rocket)
* [actix-web](actix.rs)
* [axum](https://github.com/tokio-rs/axum)
* [pavex](https://github.com/LukeMathWalker/pavex)

---
### <!--fit--> Application Server RPC
* [Prost](https://github.com/tokio-rs/prost)
* [Tonic](https://github.com/hyperium/tonic)
* [Tarpc](https://github.com/google/tarpc/)
* [Cap'n Proto](https://github.com/capnproto/capnproto-rust)

---
### <!--fit--> Serverless / WASI
* [wasmtime](https://github.com/bytecodealliance/wasmtime)
* [wasmer](https://github.com/wasmerio/wasmer)

---
### <!--fit--> Message Broker
* [zenoh](http://zenoh.io) (MQTT, DDS, ...)
* [libp2p](https://crates.io/crates/libp2p) (IPFS, DHT, ...)
* [lapin](https://crates.io/lapin) (AMQP)

---
### <!--fit--> Database Engine
* SQL
    * [gluesql](https://crates.io/crates/gluesql)
    * [datafusion](https://crates.io/crates/datafusion)
* Key-Value
    * [sled](https://crates.io/crates/sled)
    * [TiKV](https://github.com/tikv/tikv)
---
<!-- header: Ovunque? Nel tostapane! -->
# <!--fit--> Rust embedded

* Rust grazie a [`no_std`](https://docs.rust-embedded.org/book/intro/no-std.html) parte in vantaggio
    * l'approccio di avere la liberia standard "spegnibile" permette di graduare cosa si supporta
        * `std` per avere tutta la libreria standard.
        * `core` per avere solo le componenti che non devono allocare.
        * `alloc` per avere anche le parti di std che allocano.
    * Moltissimi crate nascono per funzionare anche su bare metal.
---

### <!--fit--> Hardware supportato
* [expressif](https://www.espressif.com/en/news/ESP_RUST_training) ha abbracciato Rust per le sue architetture `ESP32`.
    * in particolare la sua versione a base di RISC-V permette di fare [moltissimo](https://github.com/ivmarkov/rust-esp32-std-demo).
* [embassy](https://embassy.dev/) fornisce astrazioni asincrone e supporta molteplici sistemi
    * inclusi `STM32` e `nRF*`, oltre a `ESP32` in ogni sua forma o quasi.
* Esistono diverse `HAL` per molteplici archietture su cui poter scrivere il proprio sistema senza partire da zero.
* L'organizzazione [rust-embedded](https://github.com/rust-embedded) è un buon punto di partenza per chi è curioso.

---
### <!--fit--> Rust nelle Automobili?

* Grazie a [Ferrous System](https://ferrous-systems.com) è ora possibile usare Rust in ambito automotive ed industriale
    * Han faticato molto, ma ora esistono compilatori Rust che supportano `ISO 26262 ASIL-D` and `IEC 61508 SiL4`.
    * E se quanto stan facendo assieme all'[ESA](https://ferrous-systems.com/blog/rust-for-mission-critical-applications/) porta i suoi frutti...

---
## <!--fit--> Rust su Marte!
* O almeno oltre la troposfera.

---
<!-- header: ''-->
# <!--fit--> Conclusione

Sono ben 4 anni che parlo di Rust al LinuxDay:
* Nel **2017** ho raccontato Rust, spiegando perchè **non** lo si dovesse usare per riscrivere il mondo.
* Nel **2018** ho illustrato come mai Rust sia stato scelto per scrivere [rav1e](https://github.com/xiph/rav1e).
* Nel **2019** vi ho raccontato perchè le ragioni per non usarlo eran poche.
* **Oggi** vi ho raccontato in quanti posti potete trovarlo
    * ed in quanti altri posti lo troveremo in futuro.

---
# <!--fit--> Domande?

![center](assets/ferris-and-corro.svg)


---
## <!--fit--> Quali sono i toolkit GUI per Rust?

* [COSMIC](https://github.com/pop-os/cosmic) contribuisce ad [iced](https://github.com/iced-rs/iced) e lo usa come toolkit.
* [slint](https://github.com/slint-ui/slint) fornisce una ui con suo DSL dedicato, filosoficamente è affine a Qt.
* [egui](https://github.com/emilk/egui) è un toolkit embeddabile, utile anche per creare UI all'interno di videogiochi.

---
## <!--fit--> Abbiamo un debugger per Rust?

* __gdb__ e __lldb__ han un migliore supporto per il linguaggio, ma sono relativamente meno usati
    * Anche l'integrazione con gli IDE di intellij and Code è migliorata.
* In compenso crate come [tracing](https://github.com/tokio-rs/tracing) e [defmt](https://github.com/knurling-rs/defmt) forniscono strumenti di logging molto avanzati.

---
# Riferimenti

- [https://github.com/rust-torino](https://github.com/rust-torino) e [https://github.com/rust-italia](https://github.com/rust-italia)
- [https://github.com/lu-zero/linuxday2023](https://github.com/lu-zero/linuxday2023)
- [https://www.rust-lang.org/it/](https://www.rust-lang.org/it/)
- Twitter: [@lu\_zero\_](https://twitter.com/lu_zero_)
