# 使用 NVIDIA Brev 在云端快速运行 LeIsaac

这是开始使用 LeIsaac 的最快方式——您不需要高性能 GPU，只需要一个网页浏览器。

打开浏览器并访问此[链接](https://brev.nvidia.com/launchable/deploy/now?launchableID=env-35P96N3pyzVDW3Xlohy7X2TuLCX)。部署完成后，点击 80 端口（HTTP）的链接以打开 Visual Studio Code Server。默认密码为 `password`。

快速安装：
```bash
cd leisaac
pip install -e source/leisaac
```

我们的四个开源场景已预装，可以使用以下命令启动：
```bash
python scripts/environments/teleoperation/teleop_se3_agent.py \
    --task=LeIsaac-SO101-PickOrange-v0 \
    --teleop_device=keyboard \
    --num_envs=1 \
    --device=cuda \
    --enable_cameras \
    --kit_args="--no-window --enable omni.kit.livestream.webrtc"
```

然后您可以打开一个新的浏览器标签页来查看 UI。在此标签页中，粘贴与 Visual Studio Code 服务器相同的地址，将 URL 末尾改为 `/viewer`。

:::info[示例]
如果 VS Code Server 的地址是 `ec2.something.amazonaws.com`，那么 UI 可以通过 `ec2.something.amazonaws.com/viewer` 访问。
:::

几秒钟后，您应该能在 viewer 标签页中看到 UI。首次启动可能需要更长时间，因为需要缓存着色器。

以下是我们的演示视频：

<div style="width: 100%; max-width: 960px; margin: 0 auto;">
  <video controls preload="metadata" style="width: 100%; border-radius: 8px;">
    <source src="https://github.com/user-attachments/assets/35228eb4-6e2f-4dc1-b066-fff616ca4505" />
  </video>
</div>
