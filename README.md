<div align="center">

# Java Selenium — PageObject Pattern

**Навчальний репозиторій: автоматизоване тестування веб-застосунків на Java**

[![Java](https://img.shields.io/badge/Java_17+-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)](https://github.com/yyvolovyk-1983-edu/java-selenium-pageobject)
[![Selenium](https://img.shields.io/badge/Selenium_4.x-43B02A?style=for-the-badge&logo=selenium&logoColor=white)](https://github.com/yyvolovyk-1983-edu/java-selenium-pageobject)
[![JUnit](https://img.shields.io/badge/JUnit_5-25A162?style=for-the-badge&logo=junit5&logoColor=white)](https://github.com/yyvolovyk-1983-edu/java-selenium-pageobject)
[![Status](https://img.shields.io/badge/Status-In_Progress-yellow?style=for-the-badge)]()

</div>

---

## Реалізовано

### Алгоритми сортування

```java
int[] arr = {23, 12, 13, 17, 23, 19};

for (int i = 0; i < arr.length - 1; i++) {
    if (arr[i] > arr[i + 1]) {
        int temp = arr[i];
        arr[i]   = arr[i + 1];
        arr[i + 1] = temp;
    }
}
```

---

## Заплановано — PageObject Pattern

```java
public class LoginPage {
    private WebDriver driver;

    @FindBy(id = "username") private WebElement usernameField;
    @FindBy(id = "password") private WebElement passwordField;
    @FindBy(id = "submit")   private WebElement submitButton;

    public LoginPage(WebDriver driver) {
        this.driver = driver;
        PageFactory.initElements(driver, this);
    }

    public void login(String user, String pass) {
        usernameField.sendKeys(user);
        passwordField.sendKeys(pass);
        submitButton.click();
    }
}
```

### Test Suite з JUnit 5

```java
@ExtendWith(SeleniumExtension.class)
class LoginTest {

    @Test
    void validLoginRedirectsToDashboard() {
        LoginPage page = new LoginPage(driver);
        page.login("user@example.com", "password");
        assertEquals("https://example.com/dashboard", driver.getCurrentUrl());
    }
}
```

---

## Технічний стек

| Компонент | Версія |
|---|---|
| Java | 17+ |
| Selenium WebDriver | 4.x |
| JUnit | 5 |
| Build tool | Maven / Gradle |

---

## Roadmap

- [x] Базові алгоритми сортування (Java)
- [ ] Selenium WebDriver — базові локатори
- [ ] PageObject Pattern
- [ ] Test Suite організація
- [ ] Java Collections (HashSet, equals/hashCode)
- [ ] CI/CD інтеграція (GitHub Actions)

---

## Запуск

```bash
mvn test
```

---

<div align="center">

**Автор:** [Євген Воловик](https://github.com/yyvolovyk-1983-edu) · Харків, Україна
📧 y.y.volovyk@student.khai.edu · [LinkedIn](https://www.linkedin.com/in/yevhen-volovyk/)

</div>