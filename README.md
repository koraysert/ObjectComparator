# ObjectComparator

public class Runner {
	

	public static void main(String[] args) {
		Karsilastirilacak k = new Karsilastirilacak(1000, "abc", 'v');
		System.out.print(k.compareTo('z'));
	}

}
public class Karsilastirilacak<T> implements Comparable<T> {

	int sayi = 0;
	String s = "";
	char c = ' ';

	Karsilastirilacak(int sayi, String s, char c) {
		this.sayi = sayi;
		this.s = s;
		this.c = c;
	}

	@Override
	public int compareTo(T temp) {
		// TODO Auto-generated method stub
		// 9798100 1009897
		Integer rtn = null;
		if (temp instanceof String) {
		
			if (((String) temp).length() == (((String) this.s).length())) {
				for (int i = 0; i < (((String) temp).length()); i++) {
					if ((int) (((String) temp).toCharArray()[i]) > (int) (((String) this.s).toCharArray()[i])) {
						rtn = -1;
						break;
					} else if ((int) (((String) temp).toCharArray()[i]) < (int) (((String) this.s).toCharArray()[i])) {
						rtn = 1;
						break;
					} else if ((int) (((String) temp).toCharArray()[i]) == (int) (((String) this.s).toCharArray()[i])
							&& i == (((String) temp).length()) - 1) {
						rtn = 0;
						break;
					} else {
					}
				}

			} else if (((String) temp).length() < (((String) this.s).length())) {
				rtn = 1;
			} else
				rtn = -1;
		}

		else if (temp instanceof Integer) {

			rtn = Math.max((int) temp, this.sayi);
		} else {

			if ((int) ((temp + "").toCharArray()[0]) > (int) this.c) {
				rtn = -1;
			} else if ((int) ((temp + "").toCharArray()[0]) < (int) this.c) {
				rtn = 1;
			} else
				rtn = 0;

		}
		return rtn;
	}

}
