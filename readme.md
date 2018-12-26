<p align="center">
    <a href="https://github.com/modularbp/modular-boilerplate">
        <img src="https://user-images.githubusercontent.com/4596862/37635200-aa3271b2-2bd0-11e8-8a65-9cafa0addd67.png" height="140">
    </a>
</p>
<h1 align="center">modularCSS</h1>
<p align="center">A dead simple modular CSS architecture.</p>

## Naming
```postcss
.module .module_child .-option
```

## What
- Everything is a module.
- A module is self-contained.
- Don't modifiy other modules from it.
- The goal is reusability.

## How
- Every styled element has a class, don't use ids.
- Stick to single level, use options, not nesting.
- That way you'll keep the same low specificity and element flexibility.

## When
- Start with bigger modules.
- Don't repeat yourself.
- Break them down into smaller modules, if part of them is needed.
- Eventually, you'll know when to create new modules.

## Examples
#### Module example
```html
<div class="module">
    <div class="module_child"></div>
    <div class="module_child -option"></div>
</div>
```
```postcss
.module {
    background-color: silver;
}

.module_child {
    background-color: gray;

    &.-option {
        background-color: red;
    }
} 
```
#### Complex nesting and naming
```html
<div class="moduleName -small">
    <div class="moduleName_childName"></div>
    <div class="moduleName_childName -option"></div>
</div>
```
```postcss
.moduleName {
    background-color: silver;
    font-size: 18px;

    &.-small {
        font-size: 14px;
    }
}

.moduleName_childName {
    background-color: gray;
    padding: 40px;

    &.-option {
        background-color: red;
    }

    @nest .moduleName.-small & {
        padding: 20px;
    }
} 
```
