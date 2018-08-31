# Maillage

## Poisson

``` Shell
pdal pipeline pip_filter_sample.json
```

``` Json
{
    "pipeline":[
        {
            "filename":"in.ply",
            "spatialreference":"EPSG:2154"
        },
        {
            "type":"filters.poisson",
            "depth":9,
						"density"
        },
        {
						"type":"writers.ply",
		      	"storage_mode":"little endian",
		      	"filename":"outputfile.ply"
				}
    ]
}
```
