# `slider/Slider`

## `Test Default Structure`

####   `DOM structure is correct`

```html
<div part="slider-wrapper">
  <div part="slider">
    <div part="track-wrapper">
      <div
        part="track-fill"
        style="width:0%;"
      >
      </div>
      <div
        part="step-container"
        style="transform:translateX(-0.5%);"
      >
        <div
          part="step"
          style="transform:translateX(0.5%);background-size:1% 100%;"
        >
        </div>
      </div>
    </div>
    <div
      name="value"
      part="thumb-container"
      style="left:0%;"
    >
      <div part="pin">
        <span part="pin-value-marker">
          0
        </span>
      </div>
      <div
        draggable="true"
        part="thumb"
      >
      </div>
    </div>
  </div>
</div>

```

