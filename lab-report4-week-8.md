# Lab Report 4 - Week 8 Testing
[Back](https://bimai25.github.io/cse15l-lab-reports/index.html)
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
