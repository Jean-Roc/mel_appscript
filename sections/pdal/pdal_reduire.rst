# Réduire un nuage

## filters.sample

``` Shell
pdal translate "C:\in.ply" "C:\out.ply" sample --filters.sample.radius=20
```

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
            "type":"filters.sample",
            "radius":0.5
        },
        {
						"type":"writers.ply",
		      	"storage_mode":"little endian",
		      	"filename":"outputfile.ply"
				}
    ]
}
```
