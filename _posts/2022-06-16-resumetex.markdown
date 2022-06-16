---
layout: post
title: resumetex
date: 2022-06-16 00:00:00
description: ResumeTex is a modular and a multilingual LaTeX CV template for making application tailored CVs on the fly
---

ResumeTex is a modular and a multilingual LaTeX CV template for making application tailored CVs on the fly.

<h3 class="thick">Backstory</h3>
Until a couple of years ago, I used the CareerCup's <a href="https://www.careercup.com/resume" target="_blank">resume template</a> for the most of my applications. I also used Europass <a href="https://europa.eu/europass" target="_blank">template</a> for some other niche purposes. But as my curriculum vitae grew bigger and my applications to different positions required emphasizing certain experiences at the expense of others, it became quite the struggle to keep track of personalized resumes for different positions. Even writing customized resumes from a master CV that contains all of one's experiences, albeit faster, proved to be unsustainable with these templates for the reasons below:

1. For one, I used Microsoft Word version of the CareerCup template as I did not know LaTeX when I first started writing my CV. Sections were organized as table cells in a Microsot Word 97-2003 format which made adding, modifying, and removing sections from the resume a horrific nightmare.
2. Furthermore, using either of templates brought about a danger of vendor lock-in. CareerCup Microsoft Word template rendered inconsistently with other editors like LibreOffice Writer and Europass template can only be modified through the platform of the provider of this template.
3. Lastly, as time goes by, one ends up with multiple master CV's of different nature. For me, I ended up with at least two: An academic master CV and a professional master CV. The reason behind this is that, depending on the nature of the position one is applying to, one cannot always ommit sections and add others and call it a day. Different audiences require different styles of writing as well as levels of detail on certain sections and elements.

For those reasons, and after I felt sufficiently confident using LaTeX, I decided to switch to a LaTeX-based template. I found about the wonderful <a href="https://latexresu.me" target="_blank">Resumake</a> website, chose the first template, and started building my CV from there. Once done, I downloaded the resulting LaTeX project, and started building on it from there. While it did not completely solve my problems, it did make creating customized resumes easier and more consistent. I kept perfecting it for about two years, but I always knew that I can do better.

<h3 class="thick">Enter ResumeTex</h3>
From the difficulties explained before was born the idea of making a modular LaTeX CV template. The basic file structure of this template looks roughly like this:

{% highlight sh %}
.
├── locale-1/...
└── locale-2
    ├── 0-profile
    │   └── default.tex
    ├── 1-education
    │   ├── 1-degree-1
    │   │   └── default.tex
    │   └── 2-degree-2
    │       └── default.tex
    ├── 2-experience
    │   ├── YYYY-MM-experience-1
    │   │   ├── short.tex
    │   │   └── long.tex
    │   ├── YYYY-MM-experience-2
    │   │   ├── short.tex
    │   │   └── long.tex
    │   └── YYYY-MM-dexperience-3
    │       ├── short.tex
    │       └── long.tex
    ├── 3-skills
    │   ├── 1-traits
    │   │   ├── academia.tex
    │   │   └── pro.tex
    │   └── 2-talents
    │       ├── academia.tex
    │       └── pro.tex
    ├── 4-languages
    │   ├── 1-lang-1
    │   │   └── default.tex
    │   ├── 2-lang-2
    │   │   └── default.tex
    │   └── 3-lang-3
    │       └── default.tex
    ├── 5-projects
    │   ├── 1-project-1
    │   │   ├── short.tex
    │   │   └── long.tex
    │   ├── 2-project-2
    │   │   ├── short.tex
    │   │   └── long.tex
    │   └── 3-project-3
    │       ├── short.tex
    │       └── long.tex
    ├── 6-publications
    │   └── YYYY-MM-pub-1
    │       ├── short.tex
    │       └── long.tex
    ├── 7-honors-awards
    │   ├── YYYY-award-1
    │   │   ├── short.tex
    │   │   └── long.tex
    │   └── YYYY-award-2
    │       ├── short.tex
    │       └── long.tex
    ├── cv-1.tex
    ├── cv-2.tex
    └── cv-3.tex


{% endhighlight %}

To understand this structure, Let us first explain the simple principles guiding this design:
- `locale-n` represents on translation of your CV. This could be `en` for English, `ar` for Arabic and/or whatever you need.
- Each directory underneath specific translation is a section in the CV. The names of the directories are preceeded with a number to make ordering more obvious and visible to the naked eye.
- Underneath each subsection, there are subsection directories each representing one element of the section. The naming of each subsction directory is preceeded with either a date format that starts by the year or a number to ensure correct ordering in your favorite text editor's file eplorer.
- Each subsection can contain multiple variations of the same element in your CV (e.g. `default.tex`, `short.tex`, `long.tex`, `pro.tex`, `academia.tex`, etc.) depending on how much the writer would like to elaborate on it and how relevant it is in the specific CV that is being written. For example, you might want to use the short variation of publications in a professional CV while use the long ones in an academic CV.
- Finally, `cv-n.tex` represents a variation of your CV under the respective locale. You can create as many variations as you would like including, excluding, and mixing different variations of your CV elements. Typically, a CV variation would not have content in itself but rather reference content from subsection directories inside its locale. Other than that, the CV variation may only contain styling and template customizations. For example, this what a typical Experince section would look like inside `cv-n.tex`:


{% highlight latex %}
%==== Experience ====%
\header{Experience}
\vspace{1mm}

\input{./2-experience/YYYY-MM-experience-1/long}

\input{./2-experience/YYYY-MM-experience-2/short}

\input{./2-experience/YYYY-MM-experience-3/short}
{% endhighlight %}

- While an experience variation like `short.tex` might look like this:

{% highlight latex %}
\textbf{Company Inc.} \hfill City, Country\\
\textit{Job title} \hfill Month Year - Month Year\\
\vspace{-1mm}
\begin{itemize} \itemsep 1pt
	\item Did this and that and performed that and this.
	\item Provided services to the company such as this and that.
\end{itemize}
{% endhighlight %}

Taking Dwight K. Schrute III as an example for the ResumeTex template (just like <a href="https://latexresu.me" target="_blank">Resumake</a> because we are fans of The Office), this is what the ResumeTex English template looks like:
<div class="img_row border">
	<img class="col three" src="{{site.baseurl}}/img/posts/2022-05-06-resumetex/resumetex-en.png" alt="Old website home page">
</div>
<div class="col three caption">
	ResumeTex CV Template (English). 
</div>

<br/><br/>

<h3 class="thick">Right-to-Left: ResumeTex Arabic Template</h3>
Additionally, ResumeTex cannot only be adapted to Right-to-Left languages, but it can also be configured to mix RTL and LTR languages in the same CV. Suppose that you want to write your CV in Arabic but still want to include some English words like technical terms, company names, or any other non-translatable words. This can be done by defining Arabic as the default language in your `cv.tex` and set English as the fallback language using `babel` package. You can also set the main font for the fallback language and for Arabic via `fontspec` package. These are the lines that should be added to the `cv.tex` file:

بالإضافة إلى ما سبق، لا يمكن تكييف ResumeTex مع اللغات المكتوبة من اليمين إلى اليسار وحسب، ولكن يمكن أيضًا تهيئتها لمزج لغات تكتب من الجهتين في نفس السيرة الذاتية. لنفترض أنك تريد كتابة سيرتك الذاتية باللغة العربية ولكنك لا تزال تريد تضمين بعض الكلمات الإنجليزية مثل المصطلحات الفنية أو أسماء الشركات أو أي كلمات أخرى غير قابلة للترجمة. يمكن القيام بذلك عن طريق تحديد اللغة العربية كلغة أساسية في ملف `cv.tex` وتعيين اللغة الإنجليزية كلغة احتياطية باستخدام حزمة `babel`. يمكنك أيضًا تعيين الخط الرئيسي للغة الاحتياطية وللغة العربية عبر حزمة `fontspec`. هذه هي الأسطر التي يجب إضافتها إلى ملف `cv.tex`:

{% highlight latex %}
\usepackage[english,
            bidi=basic,
            headfoot=arabic,
            layout=counters.tabular]{babel}        
\babelprovide[import, main,
            justification=kashida,
            transforms = kashida.plain]{arabic}

\usepackage{fontspec}
\setmainfont[Scale=0.8, Ligatures=TeX]{LatinModernRoman}
\babelfont[arabic]{rm}
          [Scale=0.8, Language=Default]{Amiri}
{% endhighlight %}

Now, everything on the CV will be rendered from right to left unless specified otherwise. If you have some words that need to be rendered in a different language you need to explicitly tell LaTeX using `\foreignlanguage`. For example, a CV element in the publications section would look like this:

الآن، سيتم عرض كل شيء في السيرة الذاتية من اليمين إلى اليسار ما لم يتم تحديد العكس. إذا كانت لديك بعض الكلمات التي تحتاج إلى العرض بلغة مختلفة، فأنت بحاجة إلى إخبار LaTeX صراحةً باستخدام `\foreignlanguage`. على سبيل المثال، يمكن كتابة أحد عناصر السيرة الذاتية في قسم المنشورات الأكاديمية كما يلي:

{% highlight latex %}
\foreignlanguage{english}{
	\textbf{A Review of Information Passing 
	Techniques In Corporate Offices}} \hfill جوان 2009\\
\foreignlanguage{english}{
	\textit{ICPAS ‘09: Proceedings of the 36th 
	International Corporate Productivity Applications Symposium | June
	2009 Article No.: 20 Pages 1–7}}\\
أثبتت بمفردي أن كمية المعلومات التي يتم تمريرها خلال
ثرثرة مبردات المياه أكثر من تلك الموجودة في المذكرات الرسمية.
لاحظت أيضًا أن العمال الذين يجلبون المياه الخاصة
بهم إلى المكتب هم أسوء وضعا من غيرهم من حيث المعلومات.\\
\foreignlanguage{english}{
	\href{https://schrutefarms.com/doi/59.5531/8390495.6661890}
	{https://schrutefarms.com/doi/59.5531/8390495.6661890}}
\vspace*{2mm}
{% endhighlight %}

Taking Dwight K. Schrute III once again as an example for the ResumeTex template, this is what the Arabic template looks like:

بأخذ دوايت ك. شروت الثالث مرة أخرى كمثال لنموذج ResumeTex، هذا ما يبدو عليه نموذج اللغة العربية:


<div class="img_row border">
	<img class="col three" src="{{site.baseurl}}/img/posts/2022-05-06-resumetex/resumetex-ar.png" alt="Old website home page">
</div>
<div class="col three caption">
	نموذج ResumeTex للسير الذاتية (بالعربية).
</div>

<br/><br/>

<h3 class="thick">Make Your Own</h3>
Compiling the project is really straightforward. You have two options:

<h4 class="thick">Option 1: Overleaf</h4>
This is the simplist option. If you are an <a href="https://www.overleaf.com" target="_blank">Overleaf</a> user, you can follow these steps:
- Download the the template from GitHub as a `.zip` file.
- On Overleaf, select **New Project > Upload Project** and upload the `.zip` file you just downloaded.
- Open the project and change the compiler from `pdfLaTeX` to `LuaLaTeX` in the Settings section inside the Menu pane.
- You should now be able to compile with no problem.

<h4 class="thick">Option 2: On your Machine</h4>
Alternatively, compiling the project is really straightforward if you prefer working on your own machine. First, make sure that you set up your machine with the following requirements:
- **Tex Live Distribution:** You can get it from <a href="https://tug.org/texlive" target="_blank">here</a>.
- **ResumeTex Template**

You can then run `lualatex` command inside the directory containing your CV variant to compile your into a PDF. For example, running these commands will compile the the English ResumeTex template into a PDF inside the same directory:
{% highlight sh %}
$ cd ResumeTeX/en
$ lualatex cv.tex
{% endhighlight %}



I hope this helps someone simplify their CV making and accelerate their applications process. The template can be found on GitHub. Any feedback or suggestions are welcome.

<span class="contacticon center">
	<a href="https://github.com/iskandergaba/ResumeTex" target="_blank"><i class="fab fa-github"></i></a>
</span>
