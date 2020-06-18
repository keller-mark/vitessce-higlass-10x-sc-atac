Set up and activate conda environment:

```sh
conda env create -f environment.yml
conda activate vitessce-demo-sc-atac-seq-10x-genomics
yarn global add serve
```

Run snakemake:

```sh
snakemake --cores 1
```

Ingest the tilesets for all 10 clusters, using [higlass-server](https://github.com/higlass/higlass-server).
The script takes as an argument the relative path to the higlass server directory.

```sh
bash run_ingest.sh ../../higlass/higlass-server
```

Note: the above command may generate the following warnings `tilesets.models.DoesNotExist: Tileset matching query does not exist.`

Serve the 2 JSON files using a static file server:

```sh
serve -l 9090
```
