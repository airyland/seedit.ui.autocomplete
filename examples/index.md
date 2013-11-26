# 演示文档

---
<input id="example"/>
````javascript
seajs.use('autocomplete', function(Autocomplete){
        var $ = jQuery;
        var data = [
               'qq.com',
               '163.com',
               '126.com',
               'gmail.com'
           ];
           new Autocomplete({
               trigger: '#example',
               selectFirst: true,
               dataSource: function(query) {
                   var a = $.map(data, function(v, i) {
                       return query + '@' + v;
                   });
                   return a;
               },
               filter: '',
               inputFilter: function(v){
                   return v.replace(/^(.*)@.*$/,'$1');
               }
           }).render();
});
````
