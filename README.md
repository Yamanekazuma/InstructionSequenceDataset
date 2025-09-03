# Instruction sequences Dataset

本データセットは [[1]](https://github.com/packing-box/dataset-packed-pe) で公開されている各プログラムを対象とし，
[[2]](https://ipsj.ixsq.nii.ac.jp/records/2002144) で提案する手法を用いて命令単位での追跡を行い，N-Gramの形式にまとめたものである．

命令を表現する形式として，以下の3つの形式を用意した．

- opcode: オペコードのみをもとに一命令を表現
  ```json
  {
    "opcode": "<オペコード（例: E8）>"
  }
  ```
- mnemonic: ニーモニックのみをもとに一命令を表現
  ```json
  {
    "mnemonic": "<ニーモニック（例: call）>"
  }
  ```
- original: ニーモニックとオペランドの情報をもとに1命令を表現
  ```json
  {
    "mnemonic": "<ニーモニック（例: call）>",
    "dest": "<NonMemoryAccess|MemoryAccess{R|W|X}|None>",
    "src1": "<NonMemoryAccess|MemoryAccess{R|W|X}|None>",
    "src2": "<NonMemoryAccess|MemoryAccess{R|W|X}|None>"
  }
  ```

---

- [1] D’Hondt, A.: Dataset of packed PE samples, https://github.com/packing-box/dataset-packed-pe.
- [2] 山根一真，掛井将平，齋藤彰一：パッカーの自動解凍に向けた軽量な細粒度フック手法の提案，SIG Technical Reports 2025-CSEC-109, 情報処理学会 (2025).

