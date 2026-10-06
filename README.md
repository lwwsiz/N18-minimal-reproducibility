# N18 minimal frozen-baseline reproducibility

**[Download the executable ZIP (4.69 MB)](https://github.com/lwwsiz/N18-minimal-reproducibility/releases/download/v1.0.0/N18_minimal_reproducibility_v1.0.0.zip)**

The release contains 27 files: exact 12 prepared public-source pseudobulk input files plus `inputs.json`, unchanged baseline scientific scripts, frozen specification, expected aggregate reference, a portable reader, software versions, acquisition/preprocessing notes and a payload manifest. Only this README and one ZIP release asset are uploaded. The automatically generated GitHub source archives contain the README, not the executable package; use the attached ZIP above.

## Run

After extracting `N18_minimal_reproducibility_v1.0.0.zip`, enter its folder:

```text
python -m pip install -r requirements.txt
python -B n18_reader.py verify
python -B n18_reader.py replay-baseline --output ../N18_baseline_run_001
```

The output must be a new folder outside the package. Current verified environment: Windows 11, Python 3.12.10, NumPy 2.5.2. An earlier baseline was also verified on Linux with Python 3.12.14 / NumPy 2.3.5. Verification and replay were executed from a fresh ZIP extraction, including a path with spaces and non-ASCII characters.

**Actual release validation:** `BASELINE_REPLAY_AGREES`; 42,450 fields checked, including 37,454 numeric fields; 0 mismatches. Inputs and unchanged scientific code retained their original hashes. Exact archive SHA-256:

```text
6a40ec1816917688e696fe2a34a03fde4bf86b6e199e95c5ba286e050d8b4fc5
```

## Scope

This replays the unchanged original baseline: 450 target–stimulus–model records, including the original 25-target TGFb B0 family and original nested resampling/leave-one-out fields. It does **not** replay all current manuscript branches: later B1, finite allocations, transfers, I02 pilot/matched-guide, human pharmacology and synthetic suites remain outside this minimal entry. Their full tables/figure sources/workbooks are separate manuscript materials. Raw-source download-to-preprocessing reconstruction is not executed by this entry; the exact prepared baseline inputs are bundled instead.

The inputs are derived from public research deposits. Direct patient identifiers, patient-key maps, hospital records, cell barcodes, large raw matrices, third-party notebooks, historical cloud bundles and generated synthetic draws are not included. Read `DATA_ACQUISITION.md`, `DATA_SOURCES.json` and `RIGHTS_AND_ATTRIBUTION.md` inside the ZIP before reuse.

## Public sources and attribution

- Amrute et al., *Defining cardiac functional recovery in end-stage heart failure at single-cell resolution*, [Nature Cardiovascular Research (2023)](https://doi.org/10.1038/s44161-023-00260-8); public reheat2 pseudobulk derivative [Zenodo 10.5281/zenodo.15261569](https://doi.org/10.5281/zenodo.15261569), CC-BY-4.0.
- Aguado-Alvaro et al., *Identification of epigenetic regulators of fibrotic transformation in cardiac fibroblasts through bulk and single-cell CRISPR screens*, [Nature Communications (2025)](https://doi.org/10.1038/s41467-025-66597-9); GEO GSE261783 and supporting data [Zenodo 10.5281/zenodo.14794723](https://doi.org/10.5281/zenodo.14794723), CC-BY-4.0.
- Pinned author code/metadata and exact public-source download URLs are documented inside the ZIP. This record does not relicense upstream software or restricted resources.

N18 contributors: Wei-wei Lin (analysis and methods writing), Yin Liu (data organization), Yuan He (manuscript revision).

## 中文

请下载上方唯一的ZIP附件；GitHub自动生成的Source code ZIP只有本页说明。解压后按三条命令运行，即可从随包精确输入重算原始真实基线。实际新解压测试已通过，不需要再次索取输入或下载大型原始矩阵。新输出目录必须位于包外，且运行前不存在。

这是最小基线复现材料，不代表全文所有扩展分析已从头重算。仅发布一份说明及一个ZIP，保留来源归属与各自许可；论文正文、图片、完整补充表及工作簿未在本仓库重复上传。
