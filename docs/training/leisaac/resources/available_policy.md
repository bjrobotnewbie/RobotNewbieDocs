# 可用策略推理

此页面列出了 LeIsaac 当前支持的策略推理方法。

根据您的用例，您可能需要安装额外的依赖项以启用推理：

:::tip
对于每个支持的策略，我们都指定了已验证的提交。如果相应的仓库更新，可能会导致兼容性问题。如果遇到此类情况，请随时提交 issue。
:::

## 微调后的 gr00t n1.5

安装额外依赖项：

```shell
pip install -e "source/leisaac[gr00t]"
```

推理脚本：

```shell
python scripts/evaluation/policy_inference.py \
    --task=LeIsaac-SO101-PickOrange-v0 \
    --eval_rounds=10 \
    --policy_type=gr00tn1.5 \
    --policy_host=localhost \
    --policy_port=5555 \
    --policy_timeout_ms=5000 \
    --policy_action_horizon=16 \
    --policy_language_instruction="Pick up the orange and place it on the plate" \
    --device=cuda \
    --enable_cameras
```

:::tip
目标提交：https://github.com/NVIDIA/Isaac-GR00T/commit/4af2b622892f7dcb5aae5a3fb70bcb02dc217b96
:::

## 微调后的 gr00t n1.6

安装额外依赖项：

```shell
pip install -e "source/leisaac[gr00t]"
```

推理脚本：

```shell
python scripts/evaluation/policy_inference.py \
    --task=LeIsaac-SO101-PickOrange-v0 \
    --eval_rounds=10 \
    --policy_type=gr00tn1.6 \
    --policy_host=localhost \
    --policy_port=5555 \
    --policy_timeout_ms=5000 \
    --policy_action_horizon=16 \
    --policy_language_instruction="Pick up the orange and place it on the plate" \
    --device=cuda \
    --enable_cameras
```

:::tip
目标提交：https://github.com/NVIDIA/Isaac-GR00T/commit/e8e625f4f21898c506a1d8f7d20a289c97a52acf
:::

## Lerobot 官方策略

安装额外依赖项：

```shell
pip install -e "source/leisaac[lerobot-async]"
```

我们利用 lerobot 的异步推理功能进行策略执行。有关详细信息，请参阅[官方文档](https://huggingface.co/docs/lerobot/async)。在执行之前，请确保策略服务器正在运行。


```shell
python scripts/evaluation/policy_inference.py \
    --task=LeIsaac-SO101-PickOrange-v0 \
    --policy_type=lerobot-smolvla \
    --policy_host=localhost \
    --policy_port=8080 \
    --policy_timeout_ms=5000 \
    --policy_language_instruction='Pick the orange to the plate' \
    --policy_checkpoint_path=outputs/smolvla/leisaac-pick-orange/checkpoints/last/pretrained_model \
    --policy_action_horizon=50 \
    --device=cuda \
    --enable_cameras
```

:::tip
目标提交：https://github.com/huggingface/lerobot/tree/v0.3.3
:::

## 微调后的 openpi

安装额外依赖项：

```shell
pip install -e "source/leisaac[openpi]"
```

我们利用 openpi 的远程推理功能进行策略执行。有关详细信息，请参阅[官方文档](https://github.com/Physical-Intelligence/openpi/blob/main/docs/remote_inference.md)。在执行之前，请确保策略服务器正在运行。

```shell
python scripts/evaluation/policy_inference.py \
    --task=LeIsaac-SO101-PickOrange-v0 \
    --policy_type=openpi \
    --policy_host=localhost \
    --policy_port=8000 \
    --policy_timeout_ms=5000 \
    --policy_language_instruction='Pick the orange to the plate' \
    --device=cuda \
    --enable_cameras
```

:::tip
目标提交：https://github.com/Physical-Intelligence/openpi/commit/5bff19b0c0c447c7a7eaaaccf03f36d50998ec9d
:::
