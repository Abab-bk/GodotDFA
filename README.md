# GodotDFA

## 啥？

GDScript DFA algorithm implementation

DFA 算法的 GDSript 实现。

使用前请先在 ``` Dfa.gd ``` 中修改默认敏感词位置（DEFAULT_BLOCK_WORDS_PATH 变量）。

## 咋用？

```gdscript
@onready var yes_btn:Button = %YesBtn
@onready var dfa:DFA = $DFA as DFA


func _ready() -> void:
    yes_btn.pressed.connect(func():
        if line_edit.text == "":
            return

        if line_edit.text.length() > 7:
            show_popup("名字太长", "玩家名最长七个字")
            return

        if dfa.is_block_word(line_edit.text.dedent()):
            show_popup("违禁词", "名称包含违禁词汇，请修改")
            return
```


