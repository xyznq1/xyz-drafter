# xyz v1.2 drafter

Our drafter for PrismML's [Ternary Bonsai 2 27B](https://huggingface.co/prism-ml/Ternary-Bonsai-2-27B-gguf)
(`PTQ1_0`). It's our one-layer draft head, it reads the model's hidden states and drafts four tokens per round, and the
model checks every one of them, so you get the exact same text the model would write on its own, just faster.

With xyz-llama, our llama.cpp fork, on an RTX 4070 Ti SUPER (16 GB) at around 161k context, temperature 1.0, top-k 20,
top-p 0.95, over 10 generations (11,964 tokens): 139.5 tokens/s and 2.82 tokens per round. With xyz-engine it's
144.2 tokens/s, same text.

## Download

[`xyz-v1.2-drafter.gguf`](https://github.com/xyznq1/xyz-drafter/releases/download/v1.2/xyz-v1.2-drafter.gguf) from the
releases, SHA256 `d65671c364ae21a52fd20368393a760dbdd75f532642eab5d1cd600bdad83ac4`.

## Use it

It needs our llama.cpp fork, [xyz-llama](https://github.com/xyznq1/xyz-llama), stock llama.cpp won't load it. The
Windows release zip already has it in `models\`. If you build from source, `scripts/xyz-serve.sh` downloads it from
here on the first start, together with the model.

It only works with `Ternary-Bonsai-2-27B-PTQ1_0.gguf`, it reads that model's hidden states and uses its vocabulary.

## Credits

xyz v1.2 and its training data are ours. The draft head's design follows EAGLE-3
([arXiv:2503.01840](https://arxiv.org/abs/2503.01840)), and the model it drafts for is PrismML's Ternary Bonsai 2 27B.

## License

Apache-2.0. The file carries rows of Ternary Bonsai 2 27B's output head (PrismML, Apache-2.0), which comes from
Qwen/Qwen3.8-27B (Apache-2.0).

---

For further questions, DM us on Instagram: [@xyz_nq1](https://www.instagram.com/xyz_nq1/)
