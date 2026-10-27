# Caldera-collapse simulator (caldera_sim) and window app — companion source for the book

Design documents and code for the two-dimensional coupled simulator of caldera-forming eruptions built in ***Toward a Million Lines X — Building a Caldera-Collapse Simulator*** (Japanese title 『LLM で 100 万行のソフトウェア開発 X — カルデラ破局噴火のシミュレータを作る』; the book is in Japanese).

`caldera_sim` (Python) couples three parts in both directions: a **roof** of bonded discs (2-D discrete element method), a **magma chamber** with volatiles (0-D, with equilibrium or delayed vesiculation) and a **conduit** along the ring fault (1-D steady two-phase flow with gas–melt separation). It is used to see when an eruption stops and restarts and when the roof collapses in many small slips or in one large drop. A Windows **window app** (Flutter) sets the parameters, starts the computation, shows progress and plays the cross-section animation. **The window holds no computation of its own**: every button runs a `caldera_sim` command and reads the result files it writes. In this project **the design documents are the source of the code**.

## Download

**The ready-to-run app and the source are on the [Releases](../../releases) page**, not in this repository. The release has four separate ZIPs:

| File | Contents |
|:---|:---|
| `caldera_sim_exe.zip` | The Windows window app, ready built (**Japanese screens**), with a copy of the computation core and a `.cmd` launcher |
| `caldera_sim_exe_en.zip` | The same app (**English screens**), with the English edition of the computation core (log lines and figure text in English) |
| `caldera_sim.zip` | Design documents (`docs/`, Japanese, L1-L4, the source; `docs_en/`, the complete set for English readers: L1-L3 translated into English, L4 the Japanese originals as is) in separate folders, the code (the Japanese edition `src/` and `app/`, and the English edition `src_en/` and `app_en/`, whose log lines, figure text and window parser are in English), the 61 requirements, and empty databases (`ledger/`) |
| `caldera_sim_animations.zip` | The animations of the calculations of the book (Chapters 8-10; 26 calculations) as MP4 video files only (no GIF) |

The app needs Python 3.10 or later on your PC (see the README inside the ZIPs). There is **no APK** (the app is a Windows desktop app). The app is **not code-signed**, so Windows may warn you. Computation results (run folders) and tests are not included; the animations are in their own ZIP. No external data is needed. Computations are long (hours for the default 6-hour simulation), so try a short end time first.

You are free to change the design documents and the code and compare the results.

---

## License

- **The author holds the copyright.**
- **The code is under the GNU General Public License v3.0 or later (GPL-3.0-or-later).** The full text is [`LICENSE`](LICENSE). **If you modify it and distribute it, you must publish the source under the same GPL-3.0-or-later terms.**
- **The design documents and the text are under the Creative Commons Attribution-ShareAlike 4.0 International license (CC BY-SA 4.0).** This covers `docs/`, `docs_en/`, the READMEs and the other written text of this repository, and the text of the matching book. See [`LICENSE-DOCS.md`](LICENSE-DOCS.md).
- **If you use them, say so.** State where it came from (the title of the book and the name of this repository) and keep the copyright notice. If you changed it, say that you changed it.
- **In this project the design documents are the source of the code.** When you publish something made from this code, **publish the design documents together with the code.**
- Third-party components (numpy, scipy, numba, matplotlib installed by `pip install .`; the Flutter engine inside the EXEs) remain under their own original licenses.
- Provided "as is", without warranty — as the GPL-3.0 text says.

## 著作権とライセンス

- **著作権は、著者にあります。**
- **コードは、GNU General Public License v3.0 以降（GPL-3.0-or-later）です。**全文は [`LICENSE`](LICENSE) です。**改変して配布するときは、同じ GPL-3.0 以降の条件で、ソースを公開する義務があります。**
- **設計書と文章は、Creative Commons 表示-継承 4.0 国際（CC BY-SA 4.0）です。**このリポジトリの `docs/`・`docs_en/`・README ほかの文章と、対応する本の文章が当たります。内容は [`LICENSE-DOCS.md`](LICENSE-DOCS.md) です。
- **使ったときは、使ったことを書いてください。**どこから使ったか（本の題名と、このリポジトリの名前）と、著作権の表示を、使った先に書いてください。直したときは、直したことも書いてください。
- **このプロジェクトでは、設計書がコードの源です。**コードを使って作ったものを公開するときは、**設計書も、コードと一緒に公開してください。**
- 第三者の部品（`pip install .` で入る numpy・scipy・numba・matplotlib、EXE の中の Flutter の engine）は、それぞれの元のライセンスのままです。
- 現状のまま（as is）提供します。保証はありません（GPL-3.0 の全文のとおりです）。
