# bitbrain/godot-setup-action@main

Downloads Godot Engine and makes the binary available to you! Visit https://downloads.tuxfamily.org/godotengine/ for all available versions and pre-releases.

**Only tested with Godot 4**

## Example usage

```
jobs:
  test_action:
    runs-on: ubuntu-latest
    name: Test Action
    steps:
      - name: Checkout
        uses: actions/checkout@v3
      - name: Download Godot
        id: setup-godot
        uses: bitbrain/godot-setup-action@main
        with:
          version: 4.0
          prerelease_version: beta16
      - name: another step
        shell: bash
        run: ${{ steps.setup-godot.outputs.godot_binary }} --headless --quit -s test.gd
        
```