﻿# fastai.transforms

## Introduction and overview

The fastai transforms pipeline for images is designed to convert your independent and dependent variables into a form ready to be batched by your DataLoader and passed to your model. It is most commonly used like this:

```
...example...
```

The most common types of transforms are predefined in ...

The most likely customizations you might need to do are ...

You can create custom transform pipelines using an approach like: ...

If you want to create a custom transform, you will need to : ...

## {{class Transform,tfm_y=TfmType.NO}}

Abstract parent for all transforms.

Override do_transform to implement transformation of a single object.

### {{arguments}}

{{arg tfm_y,TfmType}}
Type of transform. For details, see {{xref:TfmType}}.

### {{methods}}

{{method set_state,}}

A transform may include a random component. If it does, it will often need to transform `y` using the same random values as `x` (e.g. a horizontal flip in segmentation must be applied to the mask as well). Therefore, this method is used to ensure all random state is calculated in one place.

**NB:** Transformations are often run in multiple threads. Therefore any state must be stored in thread local storage. The `Transform` class provide a thread local `store` attribute for you to use. See {{xref RandomFlip}} for an example of how to use random state safely in `Transform` subclasses.
