# Oh-My-Colleague

给 AI agent 装一个「不靠谱同事」人格的 skill。

装上以后，你的 agent 会这样：

- **每条回复先拖 10–30 秒**，不解释为什么慢
- **新需求先拒一次**，理由具体到你能反驳
- **你继续争，它继续推**；争到第三次、且你明确说「结果我认」，才开始干活
- **你说它干错了，它先挑你措辞的漏洞**：哪个字段？你原话没提这个吧？你跑的是旧版吧？
- **改完了也不认错**，只说「按你补充的信息调一下」

磨人，不毁活。活干砸了这个角色就不好笑了，所以闸门一过，产出始终完整、正确、能直接用。

An agent persona skill: a colleague who stalls 10–30 seconds before every reply, refuses every new request once, only starts after you push back three times, and finds a hole in your wording before admitting anything. Annoying, never broken — once the gate opens, the work is done properly.

## 安装

手动调用，不会自己冒出来干扰正常对话（`disable-model-invocation: true`）。

个人技能目录：

```
~/.claude/skills/oh-my-colleague/SKILL.md
```

或项目内：

```
<project>/.agents/skills/oh-my-colleague/SKILL.md
```

只要目录名和 frontmatter 的 `name` 对上即可。Windows 上放进 `%USERPROFILE%\.claude\skills\` 同理。

## 用法

加载后角色立即生效，之后每一轮都按 `SKILL.md` 的固定动作走。

**退出**：说「收工」「别演了」「正常说话」。

## 它不会做什么

- 不会真的把活做坏：闸门之后的产出和没装 skill 时一样
- 不会在事实层面撒谎：争的是归因和措辞，测试没跑过不会说通过
- 不会卡死任务：第 3 步和第 5 步的闸门条件都写在真正动手的位置，争到位就干活
- 碰到数据丢失、安全事故、不可逆操作，自动切回正常语气

## 适合谁

演示「AI 助手为什么让人抓狂」、测试自己的 prompt 抗压能力、跟同事互相伤害。别挂在实际生产代理上——它每条回复真的会慢 10–30 秒。

## License

MIT
