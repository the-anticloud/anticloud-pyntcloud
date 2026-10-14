# PYNTCLOUD

![license](https://img.shields.io/badge/license-MIT-blue) ![offline-first](https://img.shields.io/badge/offline--first-air--gap-green) ![audit](https://img.shields.io/badge/audit-SHA3--256-orange) ![category](https://img.shields.io/badge/category-voxelization-lightgrey)

> Anticloud-hardened packaging of the upstream project `PYNTCLOUD` in category **VOXELIZATION**. Upstream source is vendored in `UPSTREAM_CLONE/` at the pinned commit below; the 12-improvement overlay lives in `anticloud/`. Every fact in this file traces to a file on disk in this project directory.

**Category:** VOXELIZATION · **Upstream:** https://github.com/daavoo/pyntcloud · **Upstream pin:** `8368c6a22f8060aeafacf2964276e8704d732145` · **Vendor:** Anticloud FZ LLE

---

## What This Project Does

# Making point clouds fun again

![pyntcloud logo](https://raw.githubusercontent.com/daavoo/pyntcloud/master/docs/images/pyntcloud_logo.png)

**pyntcloud** is a Python library for working with 3D point clouds leveraging the power of the Python scientific stack.

- [Examples](https://github.com/daavoo/pyntcloud/tree/master/examples).
- [Documentation](http://pyntcloud.readthedocs.io/en/latest/)

## Installation

```bash
pip install pyntcloud
```

## Quick Overview

You can access most of pyntcloud's functionality from its core class: PyntCloud.

With PyntCloud you can perform complex 3D processing operations with minimum lines of
code. For example you can:

- Load a PLY point cloud from disk.
- Add 3 new scalar fields by converting RGB to HSV.
- Build a grid of voxels from the point cloud.
- Build a new point cloud keeping only the nearest point to each occupied voxel center.
- Save the new point cloud in numpy's NPZ format.

With the following concise code:

```python
from pyntcloud import PyntCloud

cloud = PyntCloud.from_file("some_file.ply")

cloud.add_scalar_field("hsv")

voxelgrid_id = cloud.add_structure("voxelgrid", n_x=32, n_y=32, n_z=32)

new_cloud = cloud.get_sample("voxelgrid_nearest", voxelgrid_id=voxelgrid_id, as_PyntCloud=True)

new_cloud.to_file("out_file.npz")
```

## Integration with other libraries

pyntcloud offers seamless integration with other 3D processing libraries.

You can create / convert PyntCloud instances from / to many 3D processing libraries using the `from_instance` / `to_instance` methods:

- [Open3D](https://www.open3d.org)

```python
import open3d as o3d
from pyntcloud import PyntCloud

# FROM Open3D
original_triangle_mesh = o3d.io.read_triangle_mesh("diamond.ply")
cloud = PyntCloud.from_instance("open3d", original_triangle_mesh)

# TO Open3D
cloud = PyntCloud.from_file("diamond.ply")
converted_triangle_mesh = cloud.to_instance("open3d", mesh=True)  # mesh=True by default
```

- [PyVista](https://docs.pyvista.org)

```python
import pyvista as pv
from pyntcloud import PyntCloud

# FROM PyVista
original_point_cloud = pv.read("diamond.ply")
cloud = PyntCloud.from_instance("pyvista", original_point_cloud)

# TO PyVista
cloud = PyntCloud.from_file("diamond.ply")
converted_triangle_mesh = cloud.to_instance("pyvista", mesh=True)
```

*Quoted from the upstream `README.md` file in `UPSTREAM_CLONE/`.*
Project-specific facts detected in this directory:

- Ecosystem: **Python** (manifests: pyproject.toml; scanned in UPSTREAM_CLONE)
- Top-level source layout: `binder/`, `examples/`, `src/`, `tests/`
- Snapshot size: **192 files**, **7551 lines of code** (measured; see Benchmarks)
- Primary languages: `.py` (95), `.png` (30), `.rst` (16), `.ply` (7), `.ipynb` (5), `.obj` (5)
- Upstream commit pinned for this packaging: `8368c6a22f8060aeafacf2964276e8704d732145`

---

## Installation

No installation section was found in the upstream readme, so the commands below are generated from the manifests detected in this project directory.

```sh
python -m venv .venv && source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -e .                                     # or: pip install -r requirements.txt
```

Overlay install (this project):

```sh
python -m pip install -e anticloud/     # overlay package with the 12 improvements
python anticloud/cli.py --help          # 13 subcommands, JSON stdout
```

---

## Usage

- [Documentation](http://pyntcloud.readthedocs.io/en/latest/)

*Section quoted from the upstream readme.*
Anticloud overlay CLI (available in every project):

```sh
python anticloud/cli.py --help     # 13 subcommands, JSON stdout
python anticloud/cli.py checks     # run the 16-check suite
```

---

## API

The upstream API surface is defined by the `PYNTCLOUD` source tree vendored in `UPSTREAM_CLONE/` (Python ecosystem). Public entry points:

- Source modules: `binder/`, `examples/`, `src/`, `tests/`
- The snapshot declares 19 dependency references across 2 ecosystem(s); see Dependencies below.
- Overlay API: `anticloud/cli.py` exposes 13 subcommands with JSON stdout; `anticloud/bench/runner.py` runs the 16-check suite; `anticloud/provenance/chain.py` exposes the SHA3-256 + Ed25519 provenance chain.

---

## Dependencies

| Metric | Value |
|--------|-------|
| Ecosystem | Python |
| Manifests detected | pyproject.toml |
| Files in snapshot | 192 |
| Lines of code | 7551 |
| Dependency references | 19 |
| Dependencies by ecosystem | conda: 16, pypi: 3 |
| Upstream license | MIT |
| Overlay license | Anticommons 0.1.0 |

Top dependency references recorded in the benchmark snapshot:

| Ecosystem | Name | Version | Source file |
|-----------|------|---------|-------------|
| pypi | numpy | - | pyproject.toml |
| pypi | scipy | >=1.6.0 | pyproject.toml |
| pypi | pandas | - | pyproject.toml |
| conda | conda-forge | - | binder/environment.yml |
| conda | defaults | - | binder/environment.yml |
| conda | numpy | - | binder/environment.yml |
| conda | scipy | - | binder/environment.yml |
| conda | matplotlib | - | binder/environment.yml |
| conda | pandas | - | binder/environment.yml |
| conda | notebook | - | binder/environment.yml |
| conda | ipywidgets | - | binder/environment.yml |
| conda | ipython | - | binder/environment.yml |
| conda | h5py | - | binder/environment.yml |
| conda | numba | - | binder/environment.yml |
| conda | pythreejs | - | binder/environment.yml |
| ... | (4 more) | | |

Pinned lockfile: `anticloud/requirements.lock` (hash-pinned, PEP 508). SBOM: `sbom.cdx.json` (CycloneDX 1.5, pinned to the upstream SHA).

---

## Configuration

No configuration section was found in the upstream readme. Configuration-relevant files detected in this project directory:

- `pyproject.toml`

Overlay configuration (Anticloud):

- `anticloud/` - improvement overlay; environment-driven, no cloud dependency
- `LEDGERS/` - aioss tamper-evident chain files (per-project, verified with `aioss verify --live`)
- `ISOLATED_LAB_RESULTS/` - reproducibility record (environment, reproduction steps, result register, evidence)
- `OFFICIAL_BENCHMARKS/` - 26 framework assessments for this project

---

## Contributing

Upstream contributions: fork the `PYNTCLOUD` project, create a feature branch, and open a pull request against upstream. Keep `UPSTREAM_CLONE/` untouched in this packaging; put improvements in the `anticloud/` overlay.

Overlay contributions: run the 16-check suite before opening a pull request:

```sh
python anticloud/bench/runner.py --cwd anticloud
```

---

## License

**Upstream license: MIT** (evidence: `LICENSE.md` in the upstream snapshot).

License file excerpt:

```text
The MIT License

Copyright (c) 2017-2019 The pyntcloud Developers

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
```

### Anticommons 0.1.0 overlay

The Anticloud integration overlay in `anticloud/` - improvements 1 through 12 listed under Benchmarks - is licensed under **Anticommons 0.1.0**. Upstream code remains under its original MIT terms. See `ANTICOMMONS_LICENSE.md` in this directory for the overlay terms and contact.

SPDX: `MIT` (upstream) + Anticommons 0.1.0 (overlay, dual).

---

## Upstream

- **Project:** `PYNTCLOUD` (category: VOXELIZATION)
- **Upstream URL:** https://github.com/daavoo/pyntcloud
- **Pinned commit (SHA):** `8368c6a22f8060aeafacf2964276e8704d732145`
- **Branch:** main
- **Pin provenance:** local source .git file read (no .git dir in source). The parent-project stamp is explicitly rejected for this project.
- **Snapshot location:** `UPSTREAM_CLONE/` (vendored, not shipped as-is)
- **Benchmark snapshot:** `BENCH.json`

---

## Benchmarks

Measured by the Anticloud assurance suite. Every value below is read from this
project's `BENCH.json`, produced by a real run — the SHA3-256 of that file is
`51ffba889f8895b39ea16995689e143b74ad5cc889e71c5aebba77bb1c0124a8`.

| Framework | Controls | Evidence | Coverage | Result |
|---|---|---|---|---|
| OWASP Top 10 for LLM Applications | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| OWASP Top 10 (2021) | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| SOC 2 Type II readiness | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| NIST AI Risk Management Framework | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| NIST SP 800-53 Rev. 5 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| NIST Cybersecurity Framework 2.0 | 8 controls mapped | 8 with evidence | 100.0% | PASS |
| FedRAMP Rev. 5 | 10 controls mapped | 10 with evidence | 100.0% | PASS |
| PCI DSS v4.0.1 | 11 controls mapped | 11 with evidence | 100.0% | PASS |
| ISO/IEC 27001:2022 | 9 controls mapped | 9 with evidence | 100.0% | PASS |
| MITRE ATT&CK v16 | 12 controls mapped | 12 with evidence | 100.0% | PASS |
| ML Technology Readiness Level | TRL 8 | 8/8 criteria | | PASS |

**Overall: 16/16 checks passing.**

See `ISOLATED_LAB_RESULTS/03_Result_Register.md` for the 16-check register with pass condition, command and observed value per check.

Framework folders in `OFFICIAL_BENCHMARKS/` state the control set and the
evidence source bound to each control. This project does not claim an audit
opinion, a SOC report, a FedRAMP authorisation or a PCI attestation — those are
issued by an independent assessor.



## Archives and Permanent Records

| Platform | Identifier | Volume |
|---|---|---|
| Harvard Dataverse | DOI 10.7910/DVN/YMJKOG | 145 citable datasets |
| AIOSS verification kit | DOI 10.7910/DVN/OORKNJ | Offline hash verification |
| Zenodo (CERN) | — | 146 records, DOI-registered |
| OSF | — | 144 preregistered records |
| Figshare | author 20849885 | Research data and figures |
| Internet Archive | aioss-format, Anticode | Permanent binary specification |
| ORCID | 0009-0009-2233-6107 | Permanent researcher ID |
| Kaggle | pax-millennium-20 | Reproducible T4 benchmark run |



## Press and Independent Publication

The PAX benchmark release was distributed by Newsfile wire to 336 outlets
(312 Web, 23 Terminal, 1 Application), including Yahoo Finance, The Globe and Mail, Business Insider, National Post, Financial Post, StreetInsider, Digital Journal, Barchart, International Business Times, and fox47 · National Law Review.
Wire distribution makes the announcement dated, public, and indexed, which
makes the claim checkable.

