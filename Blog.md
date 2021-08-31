# Blog
## Blend混合模式
[转自：https://www.bilibili.com/read/cv1874791](https://www.bilibili.com/read/cv1874791)  
[转自：https://zhuanlan.zhihu.com/p/353181370](https://zhuanlan.zhihu.com/p/353181370)
## Shader流光效果
[转自：https://blog.csdn.net/u013889563/article/details/74476738](https://blog.csdn.net/u013889563/article/details/74476738)


## https://catlikecoding.com/unity/tutorials/custom-srp/directional-shadows/  

## Shader 内发光、外发光
[转载：https://blog.csdn.net/qq_38721111/article/details/89469827](https://blog.csdn.net/qq_38721111/article/details/89469827)  
[转载：https://blog.csdn.net/wjj616806129/article/details/107642210](https://blog.csdn.net/wjj616806129/article/details/107642210)

## UGUI Sprite图集（Atlas）中Shader渲染混乱
【原因】图集的UV坐标范围为0-1，所以顶点UV存储的是该顶点在图集中的位置
【解决】将单个图片的纹理坐标保存到uv1中，传递单个图片的纹理坐标和在图集中纹理坐标的比例关系。
1.纹理坐标：
using UnityEngine;
using UnityEngine.UI;

public class VertIndexAsUV1 : BaseMeshEffect
{
    public override void ModifyMesh(VertexHelper vh)
    {
        if (!IsActive())
            return;

        UIVertex vert = new UIVertex();
        for (int i = 0; i < vh.currentVertCount; i++)
        {
            vh.PopulateUIVertex(ref vert, i);
            vert.uv1.x = (i >> 1);
            vert.uv1.y = ((i >> 1) ^ (i & 1));
            vh.SetUIVertex(vert, i);
        }
    }
}

2.比例关系：
[【转载自：https://blog.csdn.net/akof1314/article/details/50428200】](https://blog.csdn.net/akof1314/article/details/50428200)

[归一化uv坐标](https://blog.csdn.net/yinfourever/article/details/116452618)

## 内置管线Shader升级到URP
[转载](https://www.jianshu.com/p/3fef69e2efb6)

## 延迟渲染
[转载： https://medium.com/@lordned](https://medium.com/@lordned)
[转载：https://gamedevelopment.tutsplus.com/articles/forward-rendering-vs-deferred-rendering--gamedev-12342](https://gamedevelopment.tutsplus.com/articles/forward-rendering-vs-deferred-rendering--gamedev-12342)
[转载：https://www.hiagodesena.com/blog/physically-based-deferred-renderer](https://www.hiagodesena.com/blog/physically-based-deferred-renderer)
