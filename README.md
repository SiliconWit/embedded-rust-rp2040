---
title: "Embedded Rust with RP2040 - Collaboration Guide"
description: "Contributing guide for Embedded Rust with RP2040 course content"
tableOfContents: true
sidebar:
  order: 999
---

# Embedded Rust with RP2040

![Build](https://img.shields.io/badge/build-passing-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Contributors Welcome](https://img.shields.io/badge/contributors-welcome-orange)

A hands-on course covering embedded Rust programming on the Raspberry Pi Pico using the rp2040-hal and Embassy async framework. Topics include toolchain setup, ownership-driven hardware access, typestate GPIO, PWM, interrupts, async tasks, I2C/SPI with embedded-hal, UART/DMA, USB devices, Wi-Fi networking, and a multi-sensor async project.

## Lessons

| # | Title |
|---|-------|
| 1 | Rust Toolchain and First Blink |
| 2 | Ownership, Borrowing, and Hardware |
| 3 | Timers, PWM, and Interrupts |
| 4 | Embassy Async Fundamentals |
| 5 | I2C and SPI with embedded-hal |
| 6 | UART, DMA, and Ownership |
| 7 | USB Device with embassy-usb |
| 8 | Wi-Fi and Networking (Pico W) |
| 9 | Async Sensor Hub Project |

## File Structure

```
embedded-rust-rp2040/
├── index.mdx
├── rust-toolchain-first-blink.mdx
├── ownership-borrowing-hardware.mdx
├── timers-pwm-interrupts.mdx
├── embassy-async-fundamentals.mdx
├── i2c-spi-embedded-hal.mdx
├── uart-dma-ownership.mdx
├── usb-device-embassy.mdx
├── wifi-networking-pico-w.mdx
├── async-sensor-hub-project.mdx
└── README.md
```

## How to Contribute

1. Fork the repository: [SiliconWit/embedded-rust-rp2040](https://github.com/SiliconWit/embedded-rust-rp2040)
2. Create a feature branch: `git checkout -b feature/your-topic`
3. Make your changes and commit with a clear message
4. Push to your fork and open a Pull Request against `main`
5. Describe what you changed and why in the PR description

## Content Standards

- All lesson files use `.mdx` format
- Do not use `<BionicText>` in this course
- Code blocks should include a title attribute:
  ````mdx
  ```rust title="src/main.rs"
  #![no_std]
  #![no_main]
  ```
  ````
- Use Starlight components (`<Tabs>`, `<TabItem>`, `<Steps>`, `<Card>`) where appropriate
- Keep paragraphs concise and focused on practical application
- Include working code examples that compile for `thumbv6m-none-eabi`
- Lessons 1-3 use `rp2040-hal` directly; Lessons 4-9 use Embassy
- All Cargo.toml dependencies must use `embassy-rp` version 0.3 with `features = ["time-driver", "rp2040"]`
- Do not add `critical-section-single-core` to `cortex-m` (conflicts with `rp2040-hal`)

## Local Development

Clone the main site repository and initialize submodules:

```bash
git clone --recurse-submodules <main-repo-url>
cd siliconwit-com
npm install
npm run dev
```

To test a production build:

```bash
npm run build
```

## License

This course content is released under the [MIT License](LICENSE).
