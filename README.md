# Dashboard — egui Vertical and Nested Layouts

Episode 7 of the **Learn egui in Neovim** series.

A dashboard app with a vertical navigation sidebar and a details panel, built using nested horizontal and vertical layouts.

## What You'll Learn

- `ui.vertical()` to stack widgets top to bottom
- `ui.horizontal()` wrapping `ui.vertical()` for side-by-side panels
- `ui.set_max_width()` to constrain panel width
- Combining nested layouts to build a multi-panel UI

## Run

```bash
cargo run
```

## Key Code

```rust
ui.horizontal(|ui| {
    ui.vertical(|ui| {
        ui.set_max_width(150.0);
        ui.label("Navigation");
        ui.separator();
        if ui.button("Overview").clicked() {
            self.selected = String::from("Overview");
        }
    });

    ui.separator();

    ui.vertical(|ui| {
        ui.label("Details");
        ui.separator();
        ui.horizontal(|ui| {
            ui.label("Page:");
            ui.label(&self.selected);
        });
    });
});
```

## Series

This is part of the [Learn egui in Neovim](https://www.youtube.com/@CelesteAI) series, where we build Rust GUI apps step by step.
