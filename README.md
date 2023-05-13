### 02 뷰 데이터 (data) 와 메소드 (methods)
----------

#### 1. 뷰 데이터    
* 1.1 person 안에 name, age를 표시   
<pre><code>data: { 
  person: {
    name: '코지 코더',
    age: 34 
  } 
}
</code></pre> 
        
* 1.2 div 태그 내에 활용
<pre><code>{{ person.name }} {{ person.age }}   
</code></pre>
* 1.3 this.data.person.name 이 아니라 this.person.name인 이유    
     -> vue js에서 data 안에 있는 데이터들을 바로 this 안에 넣음

----------

#### 2. 메소드 
* 2.1 메소드(method) 안에 함수를 쓸 수 있고 그 함수를 사용할 수 있음    
* 2.2 메소드 내에 함수 생성    
<pre><code>methods: {
  nextYear: function() {
    return this.person.name + '는 내년에' + (this.person.age + 1) + '살 입니다'
  }
}
</code></pre>  
* 2.3 생성한 함수 사용(div)   
<pre><code>{{ nextYear() }} #함수이기 때문에 괄호를 넣어야 함    
</code></pre>
* 2.4 메소드 내에 있는 함수에서 다른 함수 호출
<pre><code>methods: {
  otherMethod: function() {
    this.nextYear();
  }
}
</code></pre>   
* 2.4 매개변수 사용
<pre><code>nextYear: function(greeting){
  return greeting
}

{{ nextYear('안녕하세요') }}
</code></pre>
* 2.5 함수를 줄여서 사용 가능
  * nextYear: function() -> nextYear()    

