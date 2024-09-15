<div align="center">

# Aspiration_Mel_Band_Roformer

A [Mel-Band-Roformer](https://arxiv.org/abs/2310.01809) model that is used to separate aspiration.
</div>

## How to use

- Clone this repository.
```bash
git clone https://github.com/SUC-DriverOld/Aspiration-Mel-Band-Roformer.git
```

- Install the requirements.
```bash
pip install -r requirements.txt
```

- Download the models.
  - Model: [aspiration_mel_band_roformer_sdr_18.9845.ckpt](./aspiration_mel_band_roformer_sdr_18.9845.ckpt)
  - Model (less aggressive): [aspiration_mel_band_roformer_less_aggr_sdr_18.1201.ckpt](./aspiration_mel_band_roformer_less_aggr_sdr_18.1201.ckpt)

- Inference.
```bash
usage: inference.py [-h] [--config_path CONFIG_PATH] [--model_path MODEL_PATH] [--input_folder INPUT_FOLDER] 
                    [--store_dir STORE_DIR] [--device_ids DEVICE_IDS [DEVICE_IDS ...]]

options:
  -h, --help                    show this help message and exit
  --config_path CONFIG_PATH     path to config yaml file
  --model_path MODEL_PATH       Location of the model
  --input_folder INPUT_FOLDER   folder with songs to process
  --store_dir STORE_DIR         path to store model outputs
  --device_ids DEVICE_IDS       list of gpu ids
```

## Description

Huggingface model repository: [https://huggingface.co/Sucial/Aspiration_Mel_Band_Roformer](https://huggingface.co/Sucial/Aspiration_Mel_Band_Roformer)<br>
You can try listening to the performance of this model [here](https://huggingface.co/Sucial/Aspiration_Mel_Band_Roformer/tree/main/example_audio).

Instruments: aspiration, other<br>
Dataset: My own datasets(171 songs for training and 17 songs for validation).<br>
Finetuned from: `model_mel_band_roformer_ep_3005_sdr_11.4360.ckpt`<br>
Configs: [config_aspiration_mel_band_roformer.yaml](./configs/config_aspiration_mel_band_roformer.yaml)

|Model Name|[aspiration_mel_band_roformer_sdr_18.9845.ckpt](https://huggingface.co/Sucial/Aspiration_Mel_Band_Roformer/blob/main/aspiration_mel_band_roformer_sdr_18.9845.ckpt)|[aspiration_mel_band_roformer_less_aggr_sdr_18.1201.ckpt](https://huggingface.co/Sucial/Aspiration_Mel_Band_Roformer/blob/main/aspiration_mel_band_roformer_less_aggr_sdr_18.1201.ckpt)|
|:---:|:---:|:---:|
|Epoch|123|27|
|Instr SDR aspiration|9.8554|9.0704|
|Instr SDR other|28.1136|27.1699|
|SDR Avg|18.9845|18.1201|

## Thanks to

- Mel-Band-Roformer [[Paper](https://arxiv.org/abs/2310.01809), [Repository](https://github.com/lucidrains/BS-RoFormer)]
- [ZFTurbo](https://github.com/ZFTurbo)'s training code [[Music-Source-Separation-Training](https://github.com/ZFTurbo/Music-Source-Separation-Training)]
- [KimberleyJensen](https://github.com/KimberleyJensen)'s simple inference code [[Mel-Band-Roformer-Vocal-Model](https://github.com/KimberleyJensen/Mel-Band-Roformer-Vocal-Model)]
- [Spacehpc](https://spacehpc.com/) provided the server for training.