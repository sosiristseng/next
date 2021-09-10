# Matplotlib figures to tiff images


Exporting pyplot figures to TIFF images with custom dpi and  LZW compression.

```julia
fig.savefig("fig.tif", dpi=300, format="tiff", pil_kwargs=Dict("compression" => "tiff_lzw"))
```

```python
fig.savefig("fig1.tif", dpi=300, format="tiff", pil_kwargs={"compression" : "tiff_lzw"})
```

<!--more-->

