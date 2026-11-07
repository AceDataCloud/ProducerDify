# Producer capability mapping

Compared with [MCPs at f0eed10abf31](https://github.com/AceDataCloud/MCPs/tree/f0eed10abf310824cb4c33d4944c63d3654ac95b/producer) and the public API contract at PlatformBackend `fa94598267a82545fb1afed6ee26bafd6cbb9ca7`.

The table maps service operations to Dify tools. Different MCP helper functions may use the same action selector or structured JSON input.

| MCP function | Dify equivalent | Notes |
|---|---|---|
| `producer_list_models` |  | Model/action selectors and the API reference; informational guidance does not submit a request. |
| `producer_list_actions` |  | Model/action selectors and the API reference; informational guidance does not submit a request. |
| `producer_get_lyric_format_guide` |  | Model/action selectors and the API reference; informational guidance does not submit a request. |
| `producer_generate_music` | `producer_generate_audios` | Set action=generate |
| `producer_generate_custom_music` | `producer_generate_audios` | Set action=generate |
| `producer_extend_music` | `producer_generate_audios` | Set action=extend |
| `producer_cover_music` | `producer_generate_audios` | Set action=cover |
| `producer_variation_music` | `producer_generate_audios` | Set action=variation |
| `producer_swap_vocals` | `producer_generate_audios` | Set action=swap_vocals |
| `producer_swap_instrumentals` | `producer_generate_audios` | Set action=swap_instrumentals |
| `producer_replace_section` | `producer_generate_audios` | Set action=replace_section |
| `producer_stems_music` | `producer_generate_audios` | Set action=stems |
| `producer_generate_lyrics` | `producer_generate_lyrics` |  |
| `producer_get_task` | `producer_task_retrieve` | Set action=retrieve |
| `producer_get_tasks_batch` | `producer_tasks_retrieve_batch` | Set action=retrieve_batch |
| `producer_upload_audio` | `producer_upload_reference_audio` |  |
| `producer_generate_video` | `producer_get_video` |  |
| `producer_generate_wav` | `producer_get_wav` |  |

## Parameter equivalents

- `producer_generate_music`: `async_` → Dify submit/poll output: async=true, stream=false.
- `producer_generate_custom_music`: `async_` → Dify submit/poll output: async=true, stream=false.
- `producer_extend_music`: `async_` → Dify submit/poll output: async=true, stream=false.
- `producer_cover_music`: `async_` → Dify submit/poll output: async=true, stream=false.
- `producer_variation_music`: `async_` → Dify submit/poll output: async=true, stream=false.
- `producer_swap_vocals`: `async_` → Dify submit/poll output: async=true, stream=false.
- `producer_swap_instrumentals`: `async_` → Dify submit/poll output: async=true, stream=false.
- `producer_replace_section`: `async_` → Dify submit/poll output: async=true, stream=false.
- `producer_stems_music`: `async_` → Dify submit/poll output: async=true, stream=false.
- `producer_get_tasks_batch`: `task_ids` → ids.

## Verification boundary

Contract examples and regression tests cover request validation, transport and task handling. Actual Dify browser cases are recorded separately in `tests/e2e-results.json` and `tests/e2e-audit.json` when available. A schema test is not a successful paid generation. Unsupported service availability and untested advanced combinations must not be described as passed.
