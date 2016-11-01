Title: My First Post
Date: 2016-11-01 19:20

Lorem ipsum dolor sit amet, oblique mentitum evertitur vis ne, usu natum definitiones et, in putant option pri. Cu eam sale nusquam, ex ius posidonium ullamcorper. In dicam ponderum eama, pro ut fugit graeci menandri, constituto mediocritatem ut nam. An case platonem sed, per ne repudiandae intellegebat definitiones, sit ex diam mundi adolescens. Timeam delicatissimi no eam, nec nibh verear no. Ad singulis pertinax eleifend his, aliquam recteque eam at.

Ut dicta libris dissentiet eam, cum te posse mundi invenire. Ne vis stet soluta epicurei, at molestie explicari similique mea. Iudico veritus eum at. Te nam agam iuvaret corrumpit. Ei sed omnis molestie temporibus, possit euismod definitiones mel no. Vim id tale vocent.

Ex vim omnis facilisis, eos ad mucius accusata vituperatoribus, ut laudem copiosae conceptam duo. Sea congue numquam theophrastus cu, eum quem clita ea, eu tibique delicatissimi cum. Eos oblique volumus at. Per ei minim nullam appetere.

Nam an reque primis qualisque, vel te pertinacia abhorreant. Noster intellegat sit ex, et eam modo wisi. Ius mazim nonumes philosophia ea, diam commodo accumsan est an. Vix percipit appellantur cu, eu volutpat efficiantur eos. Diceret impedit no his, timeam tritani sapientem in qui. Ne cum everti principes maiestatis, pertinax argumentum repudiandae vis eu.

No veri atqui commune usu, nec in denique electram, graeci numquam eu nec. An usu augue reprehendunt. Cum ex wisi soleat equidem, vim ad legimus temporibus. Sed persecuti adipiscing eu, unum essent detracto mea ei. Impetus complectitur id usu, id cum veniam fabellas deserunt, ius partem dolorem iudicabit at.

```python
import scrapy

class BlogSpider(scrapy.Spider):
    name = 'blogspider'
    start_urls = ['https://blog.scrapinghub.com']

    def parse(self, response):
        for title in response.css('h2.entry-title'):
            yield {'title': title.css('a ::text').extract_first()}

        next_page = response.css('div.prev-post > a ::attr(href)').extract_first()
        if next_page:
            yield scrapy.Request(response.urljoin(next_page), callback=self.parse)
```

