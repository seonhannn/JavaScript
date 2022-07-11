# ABOUT DOM

### BOM
웹 서비스는 웹 브라우저를 바탕으로 실행됩니다. 
이 브라우저와 관련된 객체들의 집합을 브라우저 객체 모델(BOM: Browser Object Model)이라고 부릅니다. 
이 브라우저 객체 모델(BOM)을 이용해 웹 브라우저와 관련된 기능들을 구성합니다. DOM은 이 BOM 중 하나입니다.
브라우저 객체 모델(BOM)의 최상위 객체는 window라는 객체이며, DOM은 이 window 객체의 하위 객체이기도 합니다.

<br>

### DOM
DOM은 문서 객체 모델(Document Object Model)입니다.
문서 객체란 html 문서의 태그들을 JavaScript가 이용할 수 있는 객체로 만든 것입니다.
Model은 문서 객체를 '인식하는 방식'이라고 해석할 수 있습니다.

다시 말해, DOM은 넓은 의미로 웹 브라우저가 html 페이지를 인식하는 방식을 의미합니다. 보다 좁은 의미로 보자면 document 객체와 관련된 객체의 집합을 의미할 수도 있습니다.

이러한 DOM은 tree 형식의 자료구조를 가지고 있습니다. 
tree는 하나의 root node에서 시작되어 아래로 퍼져나가는 형태입니다. 
tree에서는 위쪽의 node를 부모(parent), 아래쪽의 node를 자식(child)라고 합니다. root node는 가장 위에서 시작되는 node이므로 parent가 없는 node입니다. 그리고 child가 없는 node를 leaf node라고 합니다.

<br>

#### node
tree 구조에서 root node를 포함한 모든 개개의 개체를 node라고 표현합니다. head, body, title, h1 등의 태그와 태그 안의 텍스트 및 속성 등 모두 node에 속합니다.

<br>

#### 문서 객체 생성
문서 객체가 생성되는 방식은 두 가지로 나누어 볼 수 있습니다. 우선 웹 브라우저가 html 페이지에 적혀 있는 태그를 읽으면 생성하는 것입니다. 이런 과정을 정적으로 문서 객체를 생성한다고 말합니다. 단순히 적혀져 있는 그대로 문서 객체가 생성되는 것을 표현한 것입니다.

반대로 원래 html 페이지에 없던 문서 객체를 JavaScript를 이용해 생성할 수 있습니다. 이런 과정을 동적으로 문서 객체를 생성한다고 합니다. 

<br>

#### JavaScript로 문서 객체 생성
```
var header = document.createElement('h2');
```
document 객체에 접근하여 h2 태그를 생성합니다.
```
var textNode = document.createTextNode('Hello DOM');
```
document 객체에 접근하여 TextNode를 생성하고 스트링을 넣어줍니다.
```
header.appendChild(textNode);
```
위에서 생성한 h2 태그에 자식 노드를 추가합니다. 추가하는 자식 노드는 TextNode입니다.
```
document.body.appendChild(header);
```
documnet 객체를 통해 body 객체에 접근, body 객체에 자식 노드 추가합니다.
추가하는 자식 노드는 h2 태그에 TextNode가 자식 노드로 추가된 header입니다.

이렇게 작성하고 나면 
```<h2>Hello DOM</h2>``` 과 같은 문자가 추가됩니다.
