## Collection(map)\_20210222

```
package com.controller;

import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.Set;

import com.common.Car;

public class MapController {
	public static void main(String[] args) {
		//Map에 대해 알아보자.
		//map은 쌍으로 이루어져 있는 구조 -> key : value
		//key, value type -> 둘다 Object타입을 사용
		//통상 key값은 String으로 많이 사용함.
		//value : 객체!

		//Map은 Collection을 상속받지 않았음.
		//매소드의 명칭이나 활용이 약간 다름
		HashMap map=new HashMap();
		//값넣기 -> put(key, value);
		map.put("가","A");
		map.put("나","B");
		map.put("다","C");
		System.out.println(map);

		//저장된 값 가져오기
		//저장된 값은 key통해서 가져옴.
		//get(key);
		System.out.println(map.get("가"));
		System.out.println(map.get("나"));

		//key값은 중복이 불가능함.
		map.put("가", "유병승");
		System.out.println(map.get("가"));

		map.remove("가");

		System.out.println(map);
		System.out.println(map.get("가"));


		//map에 있는 데이터 전체 순회하기.
		// 순회하는방법 2가지
		//1. key값을 통째로 가져와 key로 접근하는방법
		//keySet() -> map의 key Set방식으로 반환하는 메소드
		Set keys=map.keySet();//key들을 반환함.

		Iterator it=keys.iterator();
		while(it.hasNext()) {
			String key=(String)it.next();//key값
			System.out.println(key+" : "+map.get(key));
		}



		//2. key,value모두 가져와 접근하는 방법
		//key,value 모두 저장하는 클래스를 이용함 -> Map.Entry클래스

		Set entrySets=map.entrySet();
		Iterator entryIt=entrySets.iterator();
		while(entryIt.hasNext()) {
			Map.Entry en=(Map.Entry)entryIt.next();
			System.out.println(en.getKey()+" : "+en.getValue());
		}


		//데이터가 있는지 확인
		System.out.println(map.isEmpty());
		System.out.println(map.containsKey("나"));
		System.out.println(map.containsValue("A"));

		//데이터의 갯수를 확인
		System.out.println(map.size());


		//데이터 전체 지우기
		map.clear();

		//map을 생성해서
		//key는 String, value Car
		// 1 : 모닝 흰색 5천 4
		// 2 : 그랜져 검은색 8천 4
		// 3 : 카니발 회색 6천 9
		// 4 : 테슬라 빨강 1억3천 4

		//1. 전체 데이터를 출력하기 (차명, 색상 가격)
		//2. 가격이 7천만원 이상인 차(차명, 가격, 인원수) 만 출력

		HashMap cars=new HashMap();
		cars.put(1, new Car("모닝","흰색",50000000,4));
		cars.put(2, new Car("그랜져","검은색",80000000,4));
		cars.put(3, new Car("카니발","회색",60000000,4));
		cars.put(4, new Car("테슬라","빨강",130000000,4));

		Set carKey=cars.keySet();
		Iterator carit=carKey.iterator();
		while(carit.hasNext()) {
			Car c=(Car)cars.get(carit.next());
			System.out.println(c.getName()+" "+c.getColor()+" "+c.getPrice());
			//System.out.println(cars.get(carit.next()));
		}

		Set entryCar=cars.entrySet();
		Iterator entryit=entryCar.iterator();

		while(entryit.hasNext()) {
			Map.Entry entry=(Map.Entry)entryit.next();
			Car c=(Car)entry.getValue();
			if(c.getPrice()>70000000) {
				System.out.println(c.getName()+" "+c.getPrice()+" "+c.getPerson());
			}

		}
	}
}




```
