# 🌧️ Thomas Demtsu

**`Comp Sci @ Cornell University (Google CSSI & TEC)`**

Hi there! I'm Thomas Demtsu, a computer science student at Cornell University. I've participated in Google's CSSI and TEC programs, where I gained hands-on experience in software development and web technologies. My passion for programming drives me to constantly learn and explore new technologies.
My web expertise lies in TypeScript, Python, Next.js, and React. I'm also experiened with Python and Java.

I have experience working with teams to develop applications, and I enjoy tackling challenging problems and delivering high-quality solutions.
In my free time, I enjoy working on personal projects and contributing to open-source software. 

Check out my GitHub repositories to see some of my work! Don't hesitate to connect with me on LinkedIn if you'd like to discuss potential collaborations. 

Don't hesitate to [connect with me](https://www.linkedin.com/in/thomas-demtsu/) to discuss potential collaborations or just to say hi!
## 📈 Stats
<br clear="left"/>
<div>
  <img align='left' width = "47%" src= "https://github-readme-stats.vercel.app/api?username=tdemtsu&hide=contribs,prs"/>
  <img align='middle' width = "34%" src= "https://github-readme-stats.vercel.app/api/top-langs/?username=tdemtsu&layout=compact"/>
</div>


## 🚀 Skills
<div>
  <img align='middle'  src="https://img.shields.io/badge/typescript-%23007ACC.svg?style=for-the-badge&logo=typescript&logoColor=white" alt="TypeScript logo">
  <img align='middle'  src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" alt="Python logo">
  <img align='middle'  src="https://img.shields.io/badge/Next-black?style=for-the-badge&logo=next.js&logoColor=white" alt="Next.js logo">
  <img align='middle'  src="https://img.shields.io/badge/react-%2320232a.svg?style=for-the-badge&logo=react&logoColor=%2361DAFB" alt="React logo">
</div>

        try {
            // Try to parse the number without specifying a region
            PhoneNumber number = phoneUtil.parse("+" + digitsOnly, null);
            return phoneUtil.isValidNumber(number);
        } catch (NumberParseException e) {
            // If parsing fails, try one more time with common country codes
            for (String prefix : new String[]{"1", "44", "86", "91"}) {
                try {
                    PhoneNumber number = phoneUtil.parse("+" + prefix + digitsOnly, null);
                    if (phoneUtil.isValidNumber(number)) {
                        return true;
                    }
                } catch (NumberParseException ignored) {
                    // Continue to the next prefix
                }
            }
            return false;
        }
    }
}
```

This updated version:

1. Doesn't require a default region.
2. Accepts phone numbers between 5 and 15 digits long (after removing non-digit characters).
3. First tries to parse the number by adding a '+' prefix.
4. If that fails, it tries parsing with some common country codes (1 for US/Canada, 44 for UK, 86 for China, 91 for India).
5. Returns true if any of these parsing attempts succeed.

Here's how you might use and test this validator:

```java
public class Main {
    public static void main(String[] args) {
        String[] testNumbers = {
            "1234567890",
            "+1 (123) 456-7890",
            "123-456-7890",
            "123.456.7890",
            "(123) 456-7890",
            "123 456 7890",
            "1234567890",
            "+441234567890",
            "00441234567890",
            "44.1234567890",
            "+1(415) 555-9876",
            "1 (415) 555-9876",
            "415-555-9876",
            "(415) 555-9876",
            "4155559876",
            "+1(415)555-9876",
            "+1(415) 555 9876",
            "+1415-555-9876",
            "+1 415.555.9876",
            "abc123def456ghi7890",
            "+8613812345678",
            "9198765432"
        };

