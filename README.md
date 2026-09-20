# hackers-cli
Expanded versions of basic Unix command-line utilities. Each of the normally pedestrian CLI tools is extended to provide more convenience and capability.

## hls: The Systems Programmer's Directory Visualizer

`hls` is a modern, systems-level directory browser built for text-as-data workflows and Unix-first environments. Designed to eliminate the friction of piping output through `awk`, `grep`, or `stat`, `hls` brings kernel-level filesystem telemetry, Git awareness, and structured JSON rendering directly into your initial directory interrogation.

### Why hls?

Where standard utilities require chaining multiple shell tools to audit low-level file states, `hls` interrogates the `stat` struct natively. 
* **Toolchain Ready:** Emit strictly typed JSON arrays (`-j`) and apply internal POSIX regex filters (`-E`) to bypass fragile text parsing.
* **Deep Inspection:** Sniff actual magic bytes (`-M`), enumerate extended attributes (`-@`), and view raw octal permissions (`-O`) alongside standard output.
* **Context Aware:** Asynchronously queries Git working trees to prepend status badges (`-G`) and safely traverses directories into cycle-proof tree graphs (`-T`).

### Building from Source

`hls` is a standalone C program with no external dependencies beyond standard POSIX headers.

```bash
# Compile with GCC or Clang
gcc -O2 -Wall -Wextra -o hls hls.c

# Install to your local path
sudo cp hls /usr/local/bin/
sudo cp hls.1 /usr/local/share/man/man1/
```

---

# Licensing
This project is authored by Bill Wear and is dual-licensed under the GNU Affero General Public License v3.0 (AGPLv3) and a Commercial License.

### Open Source / Community Use
By default, this software is released under the AGPLv3. You are entirely free to use, modify, study, and distribute this software for personal, academic, or open-source projects.

Because the AGPLv3 is a strong copyleft license, this freedom comes with a strict condition: if you modify this software, link it, or integrate it into a larger system (including providing access to its functionality over a network or as a SaaS), you must release your complete, modified source code to your users under the exact same AGPLv3 terms.

### Commercial / Proprietary Use
If you intend to integrate this software into a proprietary, closed-source commercial product, or if your organization's legal policies prohibit the use of AGPLv3-licensed software, you must acquire a separate Commercial License. This commercial agreement grants you the right to use, modify, and distribute the software in a production environment without the obligation to open-source your own proprietary derivative works.

For commercial licensing inquiries, please [e-mail me](mailto:wowear@gmail.com?subject=Commercial%20Use%20of%20hackers-cli).
