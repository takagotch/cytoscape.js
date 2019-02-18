### cytoscape.js
---
https://github.com/cytoscape/cytoscape.js

```js
var cy = cytoscape({ elements: myElements, container: myDiv });
```

```
cytoscape({

  container: document.getElementById('cy'),
  
  elements: [
    {
      group: 'nodes',
      
      data: {
        id: 'n1',
        parent: 'nparent',
      },
      scratch: {
        _foo: 'bar'
      },
      
      position: {
        x: 100,
        y: 100
      },
      
      selected: false,
      
      selectable: true,
      
      locked: false,
      
      grabbable: true,
      
      classes: ['foo', 'bar']
    },
    
    {
      data: { id: 'n2' },
      renderedPosition: { x: 200, y: 200 }
    },
    
    {
      data: { id: 'n3', parent: 'nparent' },
      position: { x: 123, y: 234}
    },
    
    {
      data: { id: 'nparent' }
    },
    
    {
      data: {
        id: 'el',
        
        source: 'n1',
        target: 'n2'
      }
    }
  ],
  
  layout: {
    name: 'preset'
  },
  
  style: [
    {
      selector: 'node',
      style: {
        'label': 'data(id)'
      }
    }
  ]
});
```

```js
var a = cy.$('#a');

var directlyConnected = a.neighborhood();

var indirectlyConnected = a.add( a.descendants() ).neighborhood();

import cytoscape from 'cytoscape';

require(['cytoscape'], function(cytoscape){
});


var cy = cytoscape({
  container: document.getElementById('cy')
});


var cy = cytoscape({
  container: $('#cy')
});

var cy = cytoscape({

  container: document.getElementById('cy'),
  
  elements: [
    {
      data: { id: 'a' }
    },
    {
      data: { id: 'b' }
    },
    {
      data: { id: 'ab', source: 'a', target: 'b' }
    }
  ],
  
  style: [
    {
      selector: 'node',
      style: {
        'background-color': '#666',
        'label': 'data(id)'
      }
    },
    
    {
      selector: 'edge',
      style: {
        'width': 3,
        'line-color': '#ccc',
        'target-arrow-color': '#ccc',
        'target-arrow-shape': 'triangle'
      }
    }
  ],
  
  layout: {
    name: 'grid',
    rows: 1
  }
  
})

var cy = cytoscape({ /**/ });

var cy = cytoscape({
  container: documnet.getElement('cy')
});

var cy = cytoscape({
  container: undefined,
  elements: [ /**/ ],
  style: [ /**/ ],
  layout: { name: 'grid', // },
  
  zoom: 1,
  pan: { x: 0, y: 0 },
  
  minZoom: 1e-50,
  maxZoom: 1e-50,
  zoomingEnabled: true,
  panningEnabled: true,
  userPanningEnabled: true,
  boxSelectionEnabled: false,
  selectionType: 'single',
  touchTapThreshold: 'single',
  touchTapThreshold: 8,
  desktopTapThreshold: 4,
  autolock: false,
  autolock: false,
  autongrabify: false,
  autonselectify: false,
  
  headless: false,
  styleEnabled: true,
  hideEdgesOnViewport: false,
  hideLabelsOnViewport: false,
  textureOnViewport: false,
  montionBlur: false,
  montionBlurOpacity: 0.2,
  wheelSensitivity: 1,
  pixelRatio: 'auto'
});

cy.add({
  group: 'nodes',
  data: { weight: 75 },
  position: { x: 200, y: 200 }
});

var eles = cy.add([
  { group: 'nodes', data: { id: 'n0' }, position: { x: 100, y: 100 }},
  { group: 'nodes', data: { id: 'n1' }, position: { x: 200, y: 200 }},
  { group: 'edges', data: { id: 'e0', source: 'n0', target: 'n1' }}
]);

var j = cy.$('#j');
cy.remove( j );

var collection = cy.elements('nodes[weight > 50]');
cy.remove( collection );

cy.remove('node[weight > 50]')


var collection = cy.collection();
cy.nodes().on('click');

var collection = cy.collection();
cy.nodes().on('click', function(e){
  var clickedNode = e.target;
  
  collection = collection.union(clickedNode);
});

cy.getElementById('j');

cy.$id('j');

cy.batch(function(){
  cy.$('#j')
    .data('weight', '70')
    .addClass('funny')
    .removeClass('serious')
});

cy.startBatch();

cy.$('#j')
  .data('weight', '70')
  .addClass('funny')
  .removeClass('serious')
;

cy.endBatch();


cy.on('tap', '', function(evt){
  var node = evt.target;
  console.log( 'tapped ' + node.id() );
});

cy.on('tap', function(event){
  
  var evtTarget = event.target;
  
  if( evtTarget === cy ){
    console.log('tap on background');
  } else {
    console.log('tap on some element');
  }
});

cy.pon('tap').then(function( event ){
  console.log('tap promise fulfilled');
});

cy.on('tap', 'node', function(){
  console.log('tap!');
});

cy.$('node').eq(0).trigger('tap');
cy.$('node').eq(1).trigger('tap');

cy.on('tap', function(){});
cy.removeListener('tap');

var handler = function(){
  console.log('called handler');
};
cy.on('tap', handler);

var otherHandler = function(){
  console.log('called other handler');
};
cy.on('tap', otherHandler);

cy.removeListener('tap', handler);


cytoscape.use( require('cy-ext') );

import ext from 'cy-ext';
cytoscape.use( ext );

var jAni = cy.$('#j').animation({
  style: {
    'background-color': 'red',
    'width': 75
  },
  duration: 1000
});

var jAni = cy.$('#j').animation({
  style: {
    height: 60
  },
  duration: 1000
});

jAni.play().promise().then(function(){
  console.log('animation done');
});

var jAni = cy.$('#j').animation({
  style: {
    'background-color': 'red',
    'width': 75
  },
  duration: 1000
});

jAni
  .play()
  .promise('completed').then(function(){
    jAni
      .reverse()
      .rewind()
      .play()
    ;
  })
;


var jAni = cy.$('#j').animation({
  style: {
    'background-color': 'red',
    'width': 75
  },
  duration: 1000
});

jAni.progress(0.5).apply();


var j = cy.$('#j');
var jAni = j.animation({
  style: {
    '': '',
    '': 75
  },
});

var eles = cy.$(':selected').remove();
eles.restore();

var ej = cy.$('#ej');

ej = ej.move({
  target: 'g'
});

cy.$('#j').on('tap', function(evt){
  console.log( 'tap ' + evt.target.id() );
});

cy.$('#j').pon('tap').then(function( evet ){
  console.log('tap promise fulfilled');
});

cy.$('node').one('tap', function(e){
  var ele = e.target;
  console.log('tapped ' + ele.id());
});

cy.node().once('click', function(e) {
  var ele = e.target;
  console.log('clicked ' + ele.id());
});

var j = cy.$('#j');
var handler = function(){ console.log('tap') };

j.on('tap', handler);

j.on('tap', function() {
  console.log('some other handler');
});

j.emit('tap');

j.removeListener('tap', handler);

j.emit('tap');

j.removeListener('tap');
```


```css
#cy {
  width: 300px;
  height: 300px;
  display: block;
}

```

```
npm install cytoscape
bower install cytoscape
npm install cytoscape
```
