# imgaug (fork with fix for NumPy 2.0+)

> 🛠️ This fork of `imgaug` includes a compatibility fix for **NumPy 2.0+**, which removed the `np.sctypes` attribute.  
> Based on a solution proposed by [@qja1998](https://github.com/qja1998) in an issue on the original repository.

---

## 🔧 What's Changed?

In `imgaug/parameters.py`, this code:

```python
NP_FLOAT_TYPES = set(np.sctypes["float"])
NP_INT_TYPES = set(np.sctypes["int"])
NP_UINT_TYPES = set(np.sctypes["uint"])
```

Has been replaced with:

```python
NP_FLOAT_TYPES = {np.float16, np.float32, np.float64}
NP_INT_TYPES = {np.int8, np.int16, np.int32, np.int64}
NP_UINT_TYPES = {np.uint8, np.uint16, np.uint32, np.uint64}
```

This resolves an `AttributeError` when using `imgaug` with NumPy 2.0 or later.

---

## 📦 Installation

Install this patched version directly using pip:

```bash
pip install git+https://github.com/pbarbadol/imgaug.git@v0.4.1-fixnp
```

---

## 📌 Requirements

- Python ≥ 3.7  
- NumPy ≥ 2.0.0  
- Based on `imgaug` v0.4.0

---

## 🙌 Credits

- Original library: [aleju/imgaug](https://github.com/aleju/imgaug)  
- Fix proposed by [@qja1998](https://github.com/qja1998)  
- Fork maintained by [@pbarbadol](https://github.com/pbarbadol)

---

## 📜 License

This fork follows the [MIT License](LICENSE) of the original project.

---

# imgaug

This Python library helps you with augmenting images for your machine learning projects.  
It converts a set of input images into a new, much larger set of slightly altered images.
