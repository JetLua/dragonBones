## dragonBones
[![npm version](https://img.shields.io/npm/v/dragonbones.js.svg?style=flat&colorB=brightgreen)](https://www.npmjs.com/package/dragonbones.js)
[![npm downloads](https://img.shields.io/npm/dm/dragonbones.js.svg?style=flat&colorB=brightgreen)](https://www.npmjs.com/package/dragonbones.js)

[官方库](https://github.com/DragonBones/DragonBonesJS/tree/master/Pixi/) 需要几处改动才能用得顺手，所以有了这个修改版。

### Install

```bash
npm i dragonbones.js
```

### Usage

```js
const
  factory = dragonBones.PixiFactory.factory,
  {resources} = loader

factory.parseDragonBonesData(resources['orad_ske.json'].data)
factory.parseTextureAtlasData(
  resources['orad_tex.json'].data,
  resources['orad_tex.png'].texture
)

const anime = factory.buildArmatureDisplay('root')
// 事件帧
anime.armature.eventDispatcher.addDBEventListener('frameEvent', async ({name}) => {
  if (name !== 'meet:end') return
  anime.animation.play('love')
  await delay(3)
  anime.animation.play('snatch')
})
anime.animation.play('meet')
anime.position.set(screen.width >> 1, screen.height + 200 >> 1)
stage.addChild(anime)
```
