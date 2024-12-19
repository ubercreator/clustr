<div align="center">

<picture>
  <source media="(prefers-color-scheme: light)" srcset="/clustr/logo1.png">
  <img alt="clustr logo" src="/clustr/logo1.png" width="50%" height="50%">
</picture>

(https://x.com/clustr_ai).


<h3>

 [Telegram](https://t.me/clustrportal) | [X](https://x.com/clustr_ai)

</h3>


</div>

---


### From source


```sh
git clone https://github.com/clustr
cd exo
pip install -e .
# alternatively, with venv
source install.sh
```


### Troubleshooting

- If running on Mac, MLX has an [install guide](https://ml-explore.github.io/mlx/build/html/install.html) with troubleshooting steps.

### Performance

- There are a number of things users have empirically found to improve performance on Apple Silicon Macs:

1. Upgrade to the latest version of MacOS 15.
2. Run `./configure_mlx.sh`. This runs commands to optimize GPU memory allocation on Apple Silicon Macs.


## Documentation

### Example Usage on Multiple MacOS Devices
