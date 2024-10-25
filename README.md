# sacd-to-flac

Download `sacd_extractor` tool:

- https://github.com/sacd-ripper/sacd-ripper/releases/download/0.3.9.3/sacd_extract-0.3.9.3-107-linux.zip

Extract the DFF files from the iso file:
```bash
./sacd_extract -2 -p -i "sample.iso" -o .
```
Convert the DFF files to FLAC:
```bash
for file in *.dff; do
    ffmpeg -i "$file" -sample_fmt s32 -ar 192000 "${file%.dff}.flac"
done
```
