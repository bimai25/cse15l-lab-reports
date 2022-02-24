# Lab Report 4 - Week 8 Testing
[Back](https://bimai25.github.io/cse15l-lab-reports/index.html)

## Repositories
[My Repository](https://github.com/bimai25/markdown-parse-brandon)

[Reviewed Repository](https://github.com/AnniePhan02/CSE15L-Panther)

## Snippet 1
### Markdown Preview
![Image](./screenshots/lab-report-4/snippet-1-prev.png)
### JUnit Tester Code
```
@Test
    public void getLinksLabReportTest1() throws IOException{
        Path fileName = Path.of("./lab-report-test-files/test-1.md");
        String contents = Files.readString(fileName);
        assertEquals(List.of("`google.com", "google.com", "ucsd.edu"),
            MarkdownParse.getLinks(contents));
    }
```
### My Implementation Tester Output
![Image](./screenshots/lab-report-4/myTest1.png)
### Reviewed Implementation Tester Output
![Image](./screenshots/lab-report-4/otherTest1.png)

## Snippet 2
### Markdown Preview
![Image](./screenshots/lab-report-4/snippet-2-prev.png)
### JUnit Tester Code
```
@Test
    public void getLinksLabReportTest2() throws IOException{
        Path fileName = Path.of("./lab-report-test-files/test-2.md");
        String contents = Files.readString(fileName);
        assertEquals(List.of("a.com", "a.com(())", "example.com"),
            MarkdownParse.getLinks(contents));
    }
```
### My Implementation Tester Output
![Image](./screenshots/lab-report-4/myTest2.png)
### Reviewed Implementation Tester Output
![Image](./screenshots/lab-report-4/otherTest2.png)

## Snippet 3
### Markdown Preview
![Image](./screenshots/lab-report-4/snippet-3-prev.png)
### JUnit Tester Code
```
@Test
    public void getLinksLabReportTest3() throws IOException{
        Path fileName = Path.of("./lab-report-test-files/test-3.md");
        String contents = Files.readString(fileName);
        assertEquals(List.of("https://www.twitter.com", "https://ucsd-cse15l-w22.github.io/", "https://cse.ucsd.edu/"),
            MarkdownParse.getLinks(contents));
    }
```
### My Implementation Tester Output
![Image](./screenshots/lab-report-4/myTest3.png)
### Reviewed Implementation Tester Output
![Image](./screenshots/lab-report-4/otherTest3.png)