# littleProblem
some little problems and bugs in my work

  # attr
  
  jquery获取checkbox的checked属性

  <input id='example' type='checkbox' checked='checked' />
  
  如果获取$('#example').attr('checked');在进入页面会获取到 'checked'，即使勾选掉checkbox，还是会获取到'checked';
  
  为此有的jquery版本发现1.8的可以正确获取。其他的试过2.1以及1.11的都会出现这个问题；
  
  最后解决发现prop方法能正确获取checkbox的checked，可能由于checked属性在html中已经写死这个属性，即使勾选掉，这个属性还在，
  
  虽然用原生js document.querySelector('#example').checked 或者$('example').get(0).checked都能正确获取到即时的checked;
  
  
  解决办法：查看资料发现jquery建议用prop而不是attr；获取用原生js获取属性
  
  小结：
  对于HTML元素本身就带有的固有属性，在处理时，使用prop方法。
  对于HTML元素我们自己自定义的DOM属性，在处理时，使用attr方法。
  再举一个例子：

  <input id="chk1" type="checkbox" />是否可见
  <input id="chk2" type="checkbox" checked="checked" />是否可见
  像checkbox，radio和select这样的元素，选中属性对应“checked”和“selected”，这些也属于固有属性，因此需要使用prop方法去操作才能获得正确的结果。

  $("#chk1").prop("checked") == false
  $("#chk2").prop("checked") == true
  如果上面使用attr方法，则会出现：

  $("#chk1").attr("checked") == undefined
  $("#chk2").attr("checked") == "checked"
  
  # aa
