# pyqt-checkbox-list-widget
PyQt QListWidget for checkable items

## Requirements
PyQt5 >= 5.8

## Setup
```pip3 install git+https://github.com/yjg30737/pyqt-checkbox-list-widget.git --upgrade```

## Included Packages
* <a href="https://github.com/yjg30737/pyqt-show-long-text-as-tooltip-list-widget.git">pyqt-show-long-text-as-tooltip-list-widget</a> - Parent class

## Example
```python
from PyQt5.QtWidgets import QCheckBox, QVBoxLayout, QWidget, QApplication
from pyqt_checkbox_list_widget.checkBoxListWidget import CheckBoxListWidget


class Widget(QWidget):
    def __init__(self):
        super().__init__()
        self.__initUi()

    def __initUi(self):
        allCheckBox = QCheckBox('Check all')
        checkBoxListWidget = CheckBoxListWidget()
        checkBoxListWidget.addItems(['a', 'b', 'c', 'd'])

        allCheckBox.stateChanged.connect(checkBoxListWidget.toggleState)

        lay = QVBoxLayout()
        lay.addWidget(allCheckBox)
        lay.addWidget(checkBoxListWidget)

        self.setLayout(lay)


if __name__ == "__main__":
    import sys

    app = QApplication(sys.argv)
    widget = Widget()
    widget.show()
    app.exec_()
```

Result

https://user-images.githubusercontent.com/55078043/145694178-9d583318-2533-43fd-bbc1-71c85444a953.mp4

## Similar package
<a href="https://github.com/yjg30737/pyqt-checkbox-table-widget.git">pyqt-checkbox-table-widget</a>

