# JavaScriptについてのお勉強(発展)

## クラスの継承

    //クラスを定義
    class hogehoge {
        constructor(el) {
            this.hoge = el;
        }
        hello(){
            alert("hello" + this.hoge);
        }
    }

    //クラスを定義しextendsでhogehogeを継承
    class hogehoge2 extends hogehoge{
        constructor(el) {
            //superにすることで親クラスのコンストラクタを使える
            super(el);
        }
        //継承したのでhello()も使える
    }

## IntersectionObserver
要素が画面に入ったときに処理を行える便利なやつ

### ~基本的な書き方

    const io = new IntersectionObserver(cb, options);//cbは呼び出したいもの、optionsはオプション
    const child = document.querySelector(".child");
    const child2 = document.querySelector(".child2");
    io.observe(child);//ここで監視が開始
    io.observe(child2);

### ~呼び出し先

    const cb = function(entries, observer){
    entries.forEach(entry => {
        if(entry.isIntersecting){
            //入ったとき
            console.log("IN")
            entry.target.classList.add("inview");//entry.targetでその対象をいじれる
            //observer.unobserve(entry.target);
            //unobserveは監視を停止する
        }
        else{
            //出たとき
            console.log("OUT")
            entry.target.classList.remove("inview");
        }
    });
    }

### ~オプションの書き方

    const options = {
        root: null,//交差対象としたい親要素を指定(bodyとかにしたいならbodyを入れる)
        rootMargin: "-300px 0px",//親要素からどれくらいめり込んでから動かすか(この場合300px上あるいは下にめり込んでから動く)
        threshold: 0//0は対象要素の1番下、1は一番上[0, 0.5, 1]と書けば上、真ん中、下で呼ばれる
    };