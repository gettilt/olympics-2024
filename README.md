<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(f"# {config['name'].title()}")
]]]-->
# Olympics 2024
<!--//[[[end]]]-->

## Mission

Tilt's mission is to map every theme to a basket of stocks for anyone to invest in. Mappings are AI generated and expert curated.
Expert improvements are accepted if they provide a better representation of a given theme.

## Theme Prompt
<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  cog.outl(config['prompt'])
]]]-->
The Paris Olympics will occur summer 2024, companies advertising during the Olympics will benefit from an uplift in sales and interest, especially companies that advertise for winning countries.
<!--[[[end]]]-->

## Theme Stocks

<!--[[[cog
import cog
import csv
import json

with open('context.json') as file:
  contexts = json.load(file)

def _get_context_str_for_ticker(ticker):
  try:
    context = contexts[ticker]
    context_str = context['chat_gpt'] or context['claude'] or ""
  except KeyError:
    context_str = ""

  return context_str

cog.outl("| Ticker  | Context | Source |")
cog.outl("| ------- | ---- | ---- |")

with open('theme.csv') as file:
  reader = csv.reader(file)
  next(reader) # skip the header
  for row in reader:
    context_str = _get_context_str_for_ticker(row[0])
    cog.outl(f"| {row[0]} | {context_str} | {row[1]} |")
]]]-->
| Ticker  | Context | Source |
| ------- | ---- | ---- |
| MCD | McDonald's, a global fast-food chain, will see increased sales and brand visibility. | chat_gpt,claude |
| SONY | Sony, through its broadcasting equipment and media presence, will benefit from the event. | chat_gpt,claude |
| BUD | Anheuser-Busch InBev, a major beer sponsor, will see increased sales and brand recognition. | chat_gpt |
| AMZN | Amazon, through its advertising and e-commerce platform, will see increased sales and visibility. | chat_gpt,claude |
| SBUX | Starbucks may see increased sales from heightened brand visibility and global presence during the Olympics. | chat_gpt,claude |
| AAPL | Apple, with its global presence and advertising, will see increased brand visibility and sales. | chat_gpt,claude |
| NKE | Nike is a major sponsor of the Olympics and will benefit from increased brand visibility and sales. | chat_gpt,twitter,claude |
| CMCSA | Comcast, through NBCUniversal, holds broadcasting rights in the U.S., benefiting from advertising revenue and viewership. | chat_gpt,google,claude |
| DIS | Disney, through ESPN, will benefit from increased sports coverage and advertising revenue. | chat_gpt,claude |
| KO | Coca-Cola is a long-time Olympic sponsor and will see a boost in global brand recognition and sales. | chat_gpt,twitter,claude |
| HMC | Honda, as a global brand, will benefit from increased advertising and sales during the Olympics. | chat_gpt |
| PEP | PepsiCo, a competitor to Coca-Cola, will also benefit from increased advertising and sales. | chat_gpt |
| T | AT&T, as a telecommunications provider, will benefit from increased data usage and advertising. | chat_gpt,claude |
| TM | Toyota, a major sponsor, will benefit from increased brand visibility and sales. | chat_gpt |
| UL | Unilever, with its wide range of consumer products, will benefit from increased advertising and sales. | chat_gpt |
| GOOGL | Alphabet, through Google and YouTube, will benefit from increased advertising revenue and viewership. | chat_gpt,google,claude |
| ABNB | Airbnb could see increased bookings in host cities and surrounding areas as fans and athletes look for accommodations during the Olympics. | twitter,claude |
| BABA |  | twitter |
| LULU |  | twitter |
| ONON |  | twitter |
| SKX |  | twitter |
| V |  | twitter,google |
| AC |  | google |
| CRM |  | google |
| CSCO |  | google |
| DXC |  | google |
| TTD |  | google |
| ROKU | Roku's streaming devices and platform could see increased adoption and engagement as viewers look for ways to watch Olympic content on their TVs. | claude |
| EXPE | Expedia Group's travel booking platforms, such as Expedia and Hotels.com, could see increased traffic and bookings as fans plan trips to attend the Olympics or visit host cities. | claude |
| UBER | Uber could see increased demand for its ride-hailing and food delivery services in host cities during the Olympics as fans and athletes navigate between venues and seek convenient transportation and dining options. | claude |
| MAR | Marriott International, as a global hotel chain, could benefit from increased bookings in host cities and nearby locations as fans, athletes, and media members seek accommodations during the Olympics. | claude |
| MA | Mastercard, like Visa, could see increased transaction volumes and brand exposure during the Olympics, especially if it secures sponsorship deals or partnerships related to the event. | claude |
<!--[[[end]]]-->

## License

<p>
This project is licensed under <a href="./LICENSE">AGPLv3</a>.
</p>


## Contributors

Thank you for your improvements! We appreciate all the contributions from the community.

<!--[[[cog
import cog
import json
with open('config.json') as file:
  config = json.load(file)
  repo = config['github_repo'].lower()
  cog.outl(f'<a href="https://github.com/gettilt/{repo}/graphs/contributors">')
  cog.outl(f'  <img src="https://contrib.rocks/image?repo=gettilt/{repo}" />')
  cog.outl('</a>')
]]]-->
<a href="https://github.com/gettilt/olympics-2024/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=gettilt/olympics-2024" />
</a>
<!--[[[end]]]-->

## Join Our Community

<a href="https://discord.gg/4vYMhRpaMY" target="_blank">
<img src="https://discord.com/api/guilds/1179775688421683220/widget.png?style=banner3" alt="">
</a>
