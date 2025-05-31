# **`openfpga-core-template` project**

Here's the **GitHub-style scaffold** for `openfpga-core-template` project. 

---

### 📁 `openfpga-core-template/` — Scaffold

```text
openfpga-core-template/
├── arch/
│   ├── arch.xml                     # VTR architecture spec
│   ├── device_grid.yaml             # OpenFPGA grid configuration
│   └── tech_mapping/
│       └── sky130_mapping.xml       # Logic-to-PDK mapping (Sky130)
│
├── rtl/
│   └── verilog/                     # Generated FPGA Verilog (from OpenFPGA)
│
├── testbenches/
│   └── test_fpga.v                  # Sample testbench for simulation
│
├── sim/
│   └── benchmarks/
│       ├── fft.v                    # Example: FFT circuit
│       ├── riscv_core.v             # Tiny RISC-V CPU
│       └── multiplier.v             # Integer multiplier
│
├── bitstream/
│   ├── format_spec.md               # Bitstream layout documentation
│   └── examples/
│       └── blink.bit                # Example bitstream
│
├── asic/
│   ├── openroad/
│   │   ├── floorplan.tcl            # OpenROAD floorplan script
│   │   ├── place.tcl
│   │   ├── route.tcl
│   │   └── final.gds
│   ├── def/
│   ├── gds/
│   └── magic/
│       └── sky130_layout.mag        # Magic layout file
│
├── io_wrappers/
│   └── caravel/                     # Caravel integration
│       ├── top_wrapper.v
│       └── pad_ring_def.json
│
├── packaging/
│   └── die_specs/
│       ├── die_outline.pdf
│       └── pad_locations.csv
│
├── scripts/
│   ├── build.sh                     # Run full build flow
│   ├── gen_bitstream.py
│   └── simulate.py
│
├── docs/
│   ├── architecture.md
│   ├── block_diagram.png
│   ├── bitstream_format.md
│   └── user_guide.md
│
├── .gitignore
├── LICENSE
├── README.md
└── config.yaml                      # Param config for tile size, LUT type, etc.
```

---

### ✅ Included Starting Points

* **`arch/`** contains your configurable architecture definitions for OpenFPGA and VTR.
* **`rtl/`** will be populated by OpenFPGA when you run the architecture generation flow.
* **`asic/openroad/`** gives you OpenROAD-ready scripts.
* **`docs/`** helps future contributors understand your design.
* **`scripts/build.sh`** will stitch together RTL + place-and-route + bitstream eventually.

---

### ⚙️ Recommended Next Steps

1. **Set up tools**:

   * Install: `yosys`, `vtr`, `openfpga`, `openroad`, `magic`, `sky130-pdk`
   * Clone: `https://github.com/lnis-uofu/OpenFPGA`, `https://github.com/verilog-to-routing/vtr-verilog-to-routing`

2. **Edit `arch.xml` and `device_grid.yaml`**:

   * Define logic blocks (LUT4 or LUT6), tile interconnects, switch boxes.

3. **Generate RTL**:

   * Use OpenFPGA to generate synthesizable Verilog

4. **Use VTR** to run a small benchmark like `fft.v` or `multiplier.v`:

   * Place-and-route
   * Analyze congestion, delay, utilization

5. **Run OpenROAD** using provided floorplan + placement + route scripts

6. **Document bitstream format** and implement a test bitstream

