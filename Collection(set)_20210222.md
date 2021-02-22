## Collection(set)\_20210222

```
package com.controller;

import java.util.ArrayList;
import java.util.HashSet;
import java.util.Iterator;
import java.util.LinkedHashSet;
import java.util.TreeSet;

import com.common.Car;

public class SetController {
	public static void main(String[] args) {

		//Set : 객체들은 저장할 수 있는 구조
		// 순서가 없고, 중복값은 저장하지않음.
		//Collection을 상속받은 객체 -> list에서 사용하는 매소드랑 비슷
		HashSet set=new HashSet();

		//값을 넣기
		set.add("곰탱이");
		set.add("야옹이");
		set.add("생선");
		set.add("고기");
		set.add("초밥");

		System.out.println(set);

		//값을 가져오기
		//set저장소에 있는 값을 가져올때는
		//값을 지칭하는 id값이 없기때문에
		//전체를 순회해야함.
		//Iterator객체를 이용하는 방법
		//forEach를 이용하는 방법
		//set.interator() 매소드를 이용함
		Iterator it=set.iterator();
		while(it.hasNext()) {
			String name=(String)it.next();
			//System.out.println(it.next());
		}
		it=set.iterator();
		it.next();

		for(Object s : set) {
			System.out.println(s);
		}

		//set의 데이터 수 알아보기
		System.out.println(set.size());
		//set.clear();
		System.out.println(set.isEmpty());

		//set에는 중복값을 가지지 않는다.!
		set.add("곰탱이");
		set.add("곰탱이");
		set.add("곰탱이");
		set.add("곰탱이");
		set.add("곰탱이");
		set.add("곰탱이");

		//출력
		Iterator it2=set.iterator();
		while(it2.hasNext()) {
			System.out.println(it2.next());
		}

		HashSet cars=new HashSet();
		cars.add(new Car("제네시스","검정",80000000,4));
		cars.add(new Car("티코","흰색",800000,2));
		cars.add(new Car("포르쉐","빨강",200000000,2));
		cars.add(new Car("마티즈","황금",40000000,4));
		cars.add(new Car("벤틀리","회색",380000000,4));

		boolean result=cars.contains(new Car("벤틀리","회색",380000000,4));

		System.out.println(result);
		cars.add(new Car("벤틀리","회색",380000000,4));
		cars.add(new Car("벤틀리","회색",380000000,4));
		cars.add(new Car("벤틀리","회색",380000000,4));
		cars.add(new Car("벤틀리","회색",380000000,4));
		cars.add(new Car("벤틀리","회색",380000000,4));

		for(Object o : cars) {
			System.out.println(o);
		}


		//lotto쉽게만들기
		HashSet lotto=new HashSet();
		while(lotto.size()!=6) {
			int num=(int)(Math.random()*44)+1;
			lotto.add(num);
		}
		for(Object o : lotto) {
			System.out.print(o+" ");
		}
		System.out.println();


		cars.remove(new Car("벤틀리","회색",380000000,4));
		for(Object o : cars) {
			System.out.println(o);
		}

		//ArrayList하고 호환성
		ArrayList list=new ArrayList();
		list.add(1);
		list.add(1);
		list.add(1);
		list.add(2);
		list.add(2);
		list.add(2);
		list.add(3);
		list.add(4);
		list.add(4);
		System.out.println(list);
		HashSet temp=new HashSet(list);
		System.out.println(temp);
		list=new ArrayList(temp);
		System.out.println(list);

		//저장 순서를 유지함.
		LinkedHashSet lSet=new LinkedHashSet();
		lSet.add("뼉다구");
		lSet.add("곰탱이");
		lSet.add("고기");
		System.out.println(lSet);

		TreeSet tSet=new TreeSet();
//		tSet.add(1);
//		tSet.add(5);
//		tSet.add(2);
//		tSet.add(3);
//		tSet.add(9);
//		tSet.add(4);
		tSet.add(new Car("제네시스","검정",80000000,4));
		tSet.add(new Car("티코","흰색",800000,2));
		tSet.add(new Car("포르쉐","빨강",200000000,2));
		tSet.add(new Car("마티즈","황금",40000000,4));
		tSet.add(new Car("벤틀리","회색",380000000,4));

		System.out.println(tSet);//자동 오름차순정렬
		Iterator it3=tSet.descendingIterator();
		while(it3.hasNext()) {
			System.out.println(it3.next());
		}

		//tSet의 데이터 중 벤틀리를 찾아서 이름, 색상, 가격 출력하기.

		Iterator carIt=tSet.iterator();
		while(carIt.hasNext()) {
			Car c=(Car)carIt.next();
			if(c.getName().contains("벤틀리")) {
				System.out.println(c.getName()+" "+c.getColor()
				+" "+c.getPrice()+" "+c.getPerson());
			}
		}



	}
}










```
