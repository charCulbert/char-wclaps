# WCLAP test plug-ins

Small fixtures for testing a WCLAP host. They are test instruments, effects,
and interfaces—not production audio products. Every archive contains
`module.wasm` and a root `LICENSE.txt`; GUI archives also contain their UI
resources.

Source: [`charCulbert/char-wclap-examples`](https://github.com/charCulbert/char-wclap-examples), local `main` commit `93a2a73` pending approved publication.

| Archive | What it tests |
| --- | --- |
| `char-example-effect.wclap.tar.gz` | Basic stereo effect loading and live/offline audio. |
| `char-example-synth.wclap.tar.gz` | MIDI instrument loading and standalone frame-zero offline startup. |
| `char-bundled-sampler.wclap.tar.gz` | Ordinary bundled sample-file loading and MIDI playback. |
| `char-note-ports-example.wclap.tar.gz` | Native CLAP notes, addresses, expressions, output events, dialects, and rescans. |
| `char-note-echo-example.wclap.tar.gz` | Sample-accurate generated note repeats, IDs, note-offs, and parameters. |
| `char-sequencer-example.wclap.tar.gz` | Transport-driven note generation across start, seek, loop, live, and offline paths. |
| `char-note-name-example.wclap.tar.gz` | Note names, wildcard addresses, changes, and host notification. |
| `char-remote-controls-example.wclap.tar.gz` | Remote-control pages, mappings, refresh, and suggestions. |
| `char-voice-info-example.wclap.tar.gz` | Voice counts, overlapping note IDs, releases, and configuration changes. |
| `char-gain-adjustment-metering-example.wclap.tar.gz` | Draft gain-adjustment metering against real limiter gain. |
| `char-audio-ports-example.wclap.tar.gz` | Audio ports, mono/stereo configurations, in-place pairs, selection, and rescans. |
| `char-audio-ports-activation-example.wclap.tar.gz` | Per-port activation and the required deactivate/change/reactivate lifecycle. |
| `char-render-example.wclap.tar.gz` | CLAP real-time/offline render-mode selection. |
| `char-thread-check-example.wclap.tar.gz` | Main/audio thread roles across lifecycle and callbacks. |
| `char-log-example.wclap.tar.gz` | All CLAP log severities from audio, main, and Worker roles. |
| `char-transport-example.wclap.tar.gz` | Every transport field, timed changes, retained state, and steady time. |
| `char-process-lifecycle-example.wclap.tar.gz` | All process statuses, sleep/wake, tail, restart, and failure silence. |
| `char-graph-failure-example.wclap.tar.gz` | Failed effect containment with exact audio bypass. |
| `char-gui-example.wclap.tar.gz` | Focused GUI create, size, show, hide, callback, and destroy lifecycle. |
| `char-gui-webview-example.wclap.tar.gz` | Multi-file WebView resources, binary messages, resizing, and parameter sync. |
| `char-gui-imgui-example.wclap.tar.gz` | Dear ImGui compiled to a separate UI Wasm, including WebGL and touch. |
| `char-gui-visage-example.wclap.tar.gz` | Visage UI Wasm, retained rendering, dials, and touch adaptation. |
| `clap-saw-demo-imgui.wclap.tar.gz` | A substantial upstream-derived synth with notes, parameters, state, voices, and ImGui. |
| `char-latency-probe.wclap.tar.gz` | Dynamic latency changes and live/offline graph compensation. |
| `char-parameters-example.wclap.tar.gz` | Parameter queries, flush, timed values, modulation, gestures, output, and callbacks. |
| `char-param-indication-example.wclap.tar.gz` | Parameter mappings and every automation-indication state. |
| `char-state-example.wclap.tar.gz` | Ordinary state save/load and dirty notification. |
| `char-state-context-example.wclap.tar.gz` | Preset, duplicate, and project state contexts plus ordinary-state compatibility. |
| `char-tail-example.wclap.tar.gz` | Dynamic tail reporting and tail-aware live/offline processing. |
| `char-presets-example.wclap.tar.gz` | Built-in and host-provided preset discovery and loading. |
| `char-security-ui-origin-probe.wclap.tar.gz` | Visible host/sibling DOM, storage, resource, message, and Service Worker attacks. |
| `char-security-ui-victim.wclap.tar.gz` | The protected sibling DOM, storage, private resource, messages, and worker. |
| `char-security-bundle-probe.wclap.tar.gz` | Intentional same-bundle sharing and isolation between separately loaded bundles. |

The two UI security plug-ins are a pair. They distinguish a request reaching a
server from JavaScript being allowed to read its response. They do not test
authenticated state changes or claim protection from outbound requests,
self-navigation, parent-domain cookies, resource exhaustion, or denial of
service.

The bundle security archive contains both victim and probe. Instances from one
loaded bundle intentionally share authority; loading the same archive again
creates the isolation boundary.

## Licenses and source

Charlie Culbert's plug-ins are MIT licensed. The same notice is embedded in
every archive.

- [CLAP](https://github.com/free-audio/clap) and
  [clap-wrapper](https://github.com/free-audio/clap-wrapper) are MIT licensed.
- `char-gui-imgui` uses [Dear ImGui](https://github.com/ocornut/imgui) under MIT.
- `char-gui-visage` uses [Visage](https://github.com/VitalAudio/visage) under
  MIT, with its required bgfx, FreeType, and font notices embedded.
- `clap-saw-demo-imgui` derives from the actual
  [CLAP Saw Demo](https://github.com/free-audio/clap-saw-demo-imgui) under MIT
  and embeds its Dear ImGui MIT and readerwriterqueue BSD-2-Clause notices.

This work belongs to the wider CLAP/WebCLAP family, including
[WebCLAP/wclap-host-cpp](https://github.com/WebCLAP/wclap-host-cpp),
[WebCLAP/wasi.wasm](https://github.com/WebCLAP/wasi.wasm), and
[WebCLAP/wclap-host-js](https://github.com/WebCLAP/wclap-host-js). Those links
record lineage; each project keeps its own terms.

This folder is a local publication draft. Do not publish it until the matching
source commit and archive set receive explicit approval.
