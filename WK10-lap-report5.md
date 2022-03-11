# Week 10 Lab Report 5 
Two test I choose are test file 507 and 508:
1. 507.md ![507](pictures/507.png)
    Expected output: []
2. 508.md ![508](pictures/508.png)
    Expected output: []

My own implementation with output:
```
public static ArrayList<String> getLinks(String markdown) {
        ArrayList<String> toReturn = new ArrayList<>();
        // find the next [, then find the ], then find the (, then take up to
        // the next )
        int currentIndex = 0;
        while(currentIndex < markdown.length()) {
            if (markdown.indexOf(")", currentIndex) == -1) {
                break;
            }
            int nextOpenBracket = markdown.indexOf("[", currentIndex);
            System.out.println(nextOpenBracket);
            int nextCloseBracket = markdown.indexOf("]", nextOpenBracket);
            int openParen = nextCloseBracket + 1; //markdown.indexOf("(", nextCloseBracket);
            char possibleOpenParam = markdown.charAt(openParen);
            if (nextOpenBracket == -1 || nextCloseBracket == -1) break;
            if (possibleOpenParam != '(') break;
            if (markdown.charAt(nextCloseBracket + 1) == '(' && (markdown.indexOf(")", currentIndex) < markdown.indexOf("[", nextCloseBracket) ||
             markdown.indexOf("[", nextCloseBracket) == -1 && markdown.indexOf(")", currentIndex) != -1)) {
                int closeParen = markdown.indexOf(")", openParen);
                toReturn.add(markdown.substring(openParen + 1, closeParen));
                currentIndex = closeParen + 1;
            } else {
                currentIndex++;
            }
        }
        return toReturn;
    }
    public static void main(String[] args) throws IOException {
		Path fileName = Path.of(args[0]);
	    String contents = Files.readString(fileName);
        ArrayList<String> links = getLinks(contents);
        System.out.println(links);
    }
```
**Output:**
```
(base) jz@Js-MacBook-Air markdown-parse % java  MarkdownParse 507.md
0
[/url "title "and" title"]
(base) jz@Js-MacBook-Air markdown-parse % java  MarkdownParse 508.md 
0
[/url 'title "and" title']
```
**Professor implementation output:** (I will not Prof's code here so I can shorten the length of the report)
```
(base) jz@Js-MacBook-Air markdown-parse % java  MarkdownParse 507.md
[]
(base) jz@Js-MacBook-Air markdown-parse % java  MarkdownParse 508.md
[]


