public String toGoatLatin(String S) {
	int len = S.length();
	int head = 0, tail = 0;
	String res = "";
	String a_repeats = "";
	for (int i = 0; i < len; i++) {
		if (S.charAt(i) == ' ' || i == len-1) {
			if(i == len-1) tail = i+1;
			else tail = i;
			char c = S.charAt(head);
			String temp = "";
			if (isVowel(c)) temp = S.substring(head,tail)+"ma";
			else temp = S.substring(head+1,tail) + S.charAt(head) + "ma";
			a_repeats = a_repeats + "a";
			if (res.length() == 0) res = temp + a_repeats;
			else res = res + " " + temp + a_repeats;
			head = tail + 1;
		}
	}
	return res;																					
}
private boolean isVowel(char c) {
	if (c == 'A' || c == 'a' || c == 'E' || c == 'e' || c == 'I' || c == 'i' ||c == 'O' || c == 'o' ||c == 'U' || c == 'u')
		return true;
	return false;
}