#Just

Mako's Haxe macros and utilities.

Current features:

*  Includes [termpose](https://github.com/makoConstruct/termpose), the sensitive markup language, an extremely flexible syntax for lists of strings

*  when you implement JustClass

   *  Generates basic constructor automatically
   
   *  Generates toTerm and fromTerm methods, which lets you express and encode your JustClasses as terms and termpose text.


Example:

```
using Just;

class Soldier implements JustClass{var name:String; var designation:String; var rank:Int;}
class Fairy implements JustClass{var name:String; var tractability:Float;}
class Bond implements JustClass{var carrier:Soldier; var ancilla:Fairy;}

class Check{
	static public function main(){
		var deployment = new Bond(
			new Soldier("mako", "diplomat", 5),
			new Fairy("faunus", 0.71));
		trace(deployment.toTerm().prettyPrint());
	}
}
```

`Bond (Soldier mako diplomat 5) (Fairy faunus 0.71)`