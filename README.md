# Chakra UI-Lesson
![Chakra UI](https://raw.githubusercontent.com/chakra-ui/chakra-ui/main/media/logo-colored@2x.png?raw=true)


# سوف نتعلم في هذا الدرس :

* التعرف على مكتبة  Chakra UI
* إضافة Chakra UI للمشروع 
* إدراج خصائص من مكتبة Chakra UI للمشروع 
* التعديل على خصائص Chakra UI
* إضافة عناصر من مكتبة Chakra UI 
* تخصيص عناصر Chakra UI 
* إدراج نماذج عمل جاهزة 
* التعديل على نماذج العمل


# مقدمة عن Chakra UI :
  مكتبة الـ[Chakra UI](https://chakra-ui.com/) هي مكتبة محتوى (component librire)  خاصة في تنسيق العناصر  ذات تصميم حديث سهل التعديل و التخصيص  و هدف من استخدام ChakraUI هو  اختصار الوقت و تخفيف الجهد على المطور بإضافة تنسيق وعناصر جاهزة وسهلة التعديل و التخصيص لتصميم الواجهات في صفحات الويب .<br />
  
  وهي تعمل مع أكثر من إطار عمل (framework) مثل :  Next.js ,Gatsby والاهم بالنسة للهذا الدرس هو React.js. 
  
  حيث تتكون مكتبة ChakraUI من عناصر جاهزةللإدراج في المشروع وقابلة للتعديل و التخصيص للتناسب العمل ومتطلباته 
  # لماذا نستعمل  Chakra UI :
  *  قابل للتخصيص بالكامل : تتيح للمستخدم الحرية الكاملة في التعديل على كامل خصائص العنصر مثل الحجم اللون الخط وغيره .
  * ـ Responsive : جميع العناصر في مكتبة ChakraUI ـ (Responsive) مع مختلف أحجام شاشات العرض.
  * دعم TypeSeript 
  * مكتبة جديدة و في تحديث مستمر 
  * إختصار الوقت باستعمال عناصر جاهزة 
  
# الأستخدام 
 : للإضافة مكتبة ChakraUI للمشروع نحتاج نقوم بتشغيل احد الأوامر التاليه 
  ```sh
  $ npm i @chakra-ui/react @emotion/react@^11 @emotion/styled@^11 framer-motion@^6
  # or
$ yarn add @chakra-ui/react @emotion/react@^11 @emotion/styled@^11 framer-motion@^6
```
بعد تثبيت المكتبة نقوم بإضافتها الى المشروع في ملف `index.tsx` بإستيراد  `ChakraProvider`من المكتبة و تغليف المشروع بـ `<ChakraProvider>` و `</ChakraProvider>`  :

```js
//index.tsx

import ReactDOM from 'react-dom/client';
import './index.css';
import App from './App';
import reportWebVitals from './reportWebVitals';
import { ChakraProvider } from '@chakra-ui/react'

const root = ReactDOM.createRoot(
  document.getElementById('root') as HTMLElement
);
root.render(
  <ChakraProvider>
    <App />
  </ChakraProvider>

);

reportWebVitals();
```

## العناصر / Components
توفر مكتبة ChakraUI  ,عناصر جاهزة للاستخدام للتوفير الكثير من الوقت و الجهد و تتميز بخصائص سهلة التعديل 
على عكس `css` جميع عناصر `chakra-ui` تبدأ بحرف كبير مثل `Box` , `Text` , `Input` :
### ـ box : 
يعد عنصر `Box` خلاصة جميع العناصر حيث يعد من العناصر الأساسية في بناء جميع العناصر الاخرى , ويحل محل `dev`
تكون أهمية إستعمال `Box` في
* تصميم واجهات متكيفه بسهولة 
* توفر إختصار من خلال تمرير `props` فا بدلا من إستعمال `backgroundColor` نستطيع إستعمال `bg` وتعطي نفس النتيجة 
* إستعمال خصائص عنصر اخر عن طريق `as` prop
```js
 <Box bg="#fff" as='button'>This is a Box</Box>

```

خطواة إستعمال box
اولا : نستدعي `Box`من مكتبة في الصفحة في هذا المثال سوف نستعمله في `app.tsx` : `@chakara-ui/react`
```js
// App.tsx

import { Box } from '@chakra-ui/react'

export default function App() {
  return (
   <Box>Hello word!</Box>
  );
};
```
يكمن استعمال `Box` مباشرة لكن يكون الاستعمال الافضل له مشابه للاستعمال `div` حيث يكون بتجميع العناصر داخل `Box` لليسهل التحكم بجميع العناصر الموجوده داخله دفعه واحده  :
```js
//App.tsx

import {
Box,
Text,
Image,
} from '@chakra-ui/react'

export default function App() {

const data = {
    imageUrl: "https://pbs.twimg.com/profile_images/1595710799556780034/cYX8qbt3_400x400.jpg",
    imageAlt: "أكادمية طويق 
    title: "معسكر تطوير مواقع الويب",
  };
  return (
  <Box maxW='sm' borderWidth='1px' borderRadius='lg' m="auto" mt="20" >
      <Image src={data.imageUrl} alt={property.imageAlt} />

      <Box 
      p='6' 
      bg="gray.300"
      boxShadow="lg"
                   >

        <Text
          mt='1'
          dir="rtl"
          fontWeight='semibold'
        >
          {data.title}
        </Text>
      </Box>
    </Box>
                  
);
};
``` 
حيث يكون المثال السابق كالتالي:
![chakraui-img01](https://lh3.googleusercontent.com/u/0/drive-viewer/AFDK6gO-ZCU0WD8HMm3nRD5MFTL9DP92wbfgq4TsWemRWlRySmRHw7NronOwWMNNdZOCiHoahS8XoVtNKOsww47Y3tmfhXtT=w1366-h657)
 <br/>نلاحظ بالإظافة للعنصر `Box` إستعملنا أيضا عنصر `Text`,`Image` ننتبه هنا انه يجب إستدعاء,`Image` `Text` من مكتبة `Chakra` :
 ```js
 //App.tsx
 import {
Box,
Text,
Image,
} from '@chakra-ui/react'
```
حيث يجب أن نستدعي أي عنص نستخدمه من مكتية `Chakra` أولا 

نلاحظ أيضا انه استعملانا مجموعة من `props` مع كلنا من `Box`,`Image`و`Text` :
```js
  <Box maxW='sm' borderWidth='1px' borderRadius='lg' m="auto" mt="20px" >
      
```
### خصائص `Box` :
 * #### ـ`maxW`= maxWidth: يحدد الحد الأقصى لعرض العنصر وتحدد قيمتة بـ وحدات الحجم `px,rem,em,...` , او بالقيم الجاهزة من مكتبة `Chakra` حيث يكون `lx`للكبير و `sm`للمتوسط و `xs`للصغير . 
* #### ـ`borderWidth` : يحدد عرض حدود العنصر .
#### ـ`borderRadius` : يحدد مقدار انحنى زوايا العنصر  , حيث يحول من اطراف حاده الى اطراف منحنيه ويمكن تحديد قمته من خلال `sm, md, lg`.
#### ـ`m` =  Margin :مماثلة للموجوده في `CSS` وهي تحدد المسافه الفاصله بين العنصر و الحدود الاخرى المحيطة به, هنا إستعملنا قيمة `auot` .
#### ـ`mt` = Margin Top :مشابهة للسابقتها لكنها تحدد القيمه بين العنصر و الحد الاعلى منه, إستعملنا قمتة `20px` .


### Text 
### ـ`Text`: تحل محل paragraphs `p` حيث يمكن كتابة اي نص داخلها وعرضها في الواجهة 
### خصائص `Text` :
بعد إستعاء `Text` من مكتبة `Chakra` نستعملها كا التالي :
```js 
        <Text
          mt='1'
          dir="rtl"
          fontWeight='semibold'
        >
          {data.title}
        </Text>
       
 ```
نلاحظ هنا اننا إستدعينا قيمة النص من `{data.title}` ويمكن ايضا كتابتة مباشرا 
```js
    <Text
          mt='1'
          dir="rtl"
          fontWeight='semibold'
        >
          eمعسكر تطوير مواقع الويب
        </Text>
```

#### ـ`dir`:تحدد باتجاه بداية النص حيت تكون القيمة الأفتراضية للنص من اليسار لليمين `ltr`, و للنحدد قيمتها للـتبدا من اليمين للـيسار نظيف قمتة `rtl` .
#### ـ`fontweight` : يحدد عرض النص او بصوره ادق كمية الحبر في النص وهنا حدد قيمة `semibold` و من القيم الاخرى `bold` , `normal` .

### ـ Image :
 يتعمل عنصر `Image` لعرض الصور مع خيار بديل في حال عدم عرض الصورة .
### خصائص `Image` :

```js
      <Image src={data.imageUrl} alt={property.imageAlt} />
```
كما وضحنا في المثال السابق إستدعينا قيمة `src` من `data` ويمكن ايضا كتابة مباشرة :
```js
<Image src="https://pbs.twimg.com/profile_images/1595710799556780034/cYX8qbt3_400x400.jpg" alt="شعار أكادمية طويق " />

```
#### ـ`src`: يحدد مصدر الصوره 
#### ـ`alt` : النص البديل يظهر للمستخدم في حالة تعطل الصورة 

### ـ`SimpleGrid` 

توفر `SimpleGrid` طريقة سهلة للتنسيق العناصر في ` responsive grid ` للنتاسب جميع أحجام أجهزة العرض , حيث تقوم بتقسيم شاشة العرض الى اعمدة و صفوف وتحديد عدد الصفوف في العرض عند نقاط معينة في عرض الشاشه :
```js
 <SimpleGrid
          columns={{ base: 1, md: 2, lg: 3 }}
        > 
```
حددنا في المصفوف عدد صفوف العرض و ونقطة التحول :
* تكون `base` من `0em`الى `48em`
* تكون `md` من `48em`الى `80em`
* وتكون `lg` من `80em` و أعلى 

أولا نستدعي `simpleGraid` من مكتبة `Chakra UI ` :
```js
//App.tsx
import {Image,SimpleGrid} from "@chakra-ui/react";
```
نضيفها الان للمشروع 
```js 
import {Image,SimpleGrid} from "@chakra-ui/react";

export default function App() {

  return (
    <SimpleGrid
          columns={{ base: 1, md: 2, lg: 3 }}
          spacing={20}
          px={{ base: 1, lg: 16, xl: 24 }}
          py={20}
          mx="auto"
        > 
        <Image src="https://pbs.twimg.com/profile_images/1595710799556780034/cYX8qbt3_400x400.jpg" alt="شعار أكادمية طويق " />
        <Image src="https://pbs.twimg.com/profile_images/1595710799556780034/cYX8qbt3_400x400.jpg" alt="شعار أكادمية طويق " />
        <Image src="https://pbs.twimg.com/profile_images/1595710799556780034/cYX8qbt3_400x400.jpg" alt="شعار أكادمية طويق " />
        <Image src="https://pbs.twimg.com/profile_images/1595710799556780034/cYX8qbt3_400x400.jpg" alt="شعار أكادمية طويق " />
        <Image src="https://pbs.twimg.com/profile_images/1595710799556780034/cYX8qbt3_400x400.jpg" alt="شعار أكادمية طويق " />
        <Image src="https://pbs.twimg.com/profile_images/1595710799556780034/cYX8qbt3_400x400.jpg" alt="شعار أكادمية طويق " />
    </SimpleGrid>
      
  );
};
```
ليكون ناتج الكود السابق في الحجم الكامل عند عرض `lg` :
![chakra-ui-img02](https://lh3.googleusercontent.com/u/0/drive-viewer/AFDK6gMC530VplxkiocgYA_HEaWRKvsaJxf0V20fULTqOx5IP84vMTiUnGW3a0AOs4Fd4p8Dh7WqF8ukrOgVwQ1AyMCMn_SFgg=w1366-h657)
نلاحظ انه قام بقسيم الى ثلاث اعمده , ومهما زاد عرض الشاشه يضل توزيع العناصر نفسه .

والان نقلص العرض لنصل الى نقطة التحول الاولى `md` لتكون النتيجة :
![chakra-ui-img03](https://lh3.googleusercontent.com/u/0/drive-viewer/AFDK6gMqex22A-FMxDoWYVI55YXofP230H7VOYuKIAZAP7uWJWatrJTlDlwwSMiwGLSMYPKjNC3ONzn4zpHzyxJUwkeYv0pk=w969-h657)
نلاحظ انه تحول التقسيم الى عمودين ولكن لاتزل العناصر تحتفظ بخصائصها .

عد الوصول للحد الادنى `base` يقل التقسيم الى صف واحد : 
![chakra-ui-img04](https://lh3.googleusercontent.com/u/0/drive-viewer/AFDK6gMIbrfEJHoDFxCMrXc0o-6BrYvKMHlGReKfsuVtHo-xqyNeWNmIUTqBYUMdPvRVASIJr30K86PlQ3lcULd1HGhfd5OHVQ=w969-h657)







 ## النماذج / Templates 
 يتميز ChakraUI بوجود نماذج جاهز للإضافة للمشروعك و تعديل عليها لكي تناسب مشروعك ,و  من اشهر هذه المواقع [chakra templates](https://chakra-templates.dev/) , [choc-ui](https://choc-ui.com/) .
في هذا المثال سوف نضيف `navbar` ونعدل خصائصه لتناسب المشروع اول دخل على , [choc-ui](https://choc-ui.com/) نختار من القائمة الجانبية خيار `navbar` :
![chakra-ui-img05](https://lh3.googleusercontent.com/u/0/drive-viewer/AFDK6gNhpaiuON1Zve5cvtINaCARNaM63B1J0UTysnSLW_2aaiYarzON49EtoKEoxLQUHrURF4VnP5lq-YzzrqW3gozNQp66=w1366-h657)
الان نختار نموذج جاهز و لكون الاول نتختار خيار عرض الـكود :
![chakra-ui-img06](https://lh3.googleusercontent.com/u/0/drive-viewer/AFDK6gO-ABjxRJPqa8p0LjhnvGRLjY5nm8coytYsrySYj6yPGkju_zr-AYMtZ45GogWZS-ZrVKxgrCe-ID_EhfrPc1QJnMPf=w1366-h657)
ننسخ الكود في الصفحة :
![chakra-ui-img07](https://lh3.googleusercontent.com/u/0/drive-viewer/AFDK6gNqnfBnuIFbYOlOrf_B2Zu76-ERwXEkroIfWyNTzvlkS5m6L-9Qlf0SbeRn__TiEYKuKaxezoxjuDg90O63NFU3C0C_=w1366-h657)
ننسخ الكود بالكامل نلصقه في صفحة `comp` المخصصه له :
![chakra-ui-img07](https://lh3.googleusercontent.com/u/0/drive-viewer/AFDK6gM_EeA1-6q-6yrBa4qLEAYO8ekOIuAcxrRizKPgFfmTq6OXH_SjljT4XjN505EJQ-2y1pQey2nM6Ic8QPyCXFDNSZO8=w2184-h1340)
مهم : نلاحظ ان اسم `function` يجب تغيره الى `Navbar` :
![chakra-ui-img08](https://lh3.googleusercontent.com/u/0/drive-viewer/AFDK6gMkFduR-djyyZUcUZN2EC3W1cPgfj9FoyB2KMZ7HAmJeSjLyfgM7TzQEDMo6WlGQbEDPK62Y9NHLioFvQO7YGzlpecJog=w1366-h657)
لانن نريد ان يكون `navbar` في جميع الصفحات نضيفه مباشرة للملف `index.tsx` :
* أولا : نستعيه من مجلد `components` :
```js 
// index.tsx
import Navbar from './components/navbar';
```
* ثانيا : نظيفة بعد `  <ChakraProvider >` :
```js
  <ChakraProvider>
    <Navbar />
    <App />
  </ChakraProvider>
  ```
  
  الان يكون شكل المشروع كالتالي :
  ![chakra-ui-img09](https://lh3.googleusercontent.com/u/0/drive-viewer/AFDK6gM-k5OCvC6z0QQKeV5jQkAl3lVYOVKR8VUnSpjeAmgGHjTa1LGquSsLkpm78gM2F0fdR9tOXVUYd6pr-z0x4lmQHJb1=w1366-h657)
  وللأجهزة الجوال :
  ![chakra-ui-img10](https://lh3.googleusercontent.com/u/0/drive-viewer/AFDK6gOdDNj-93rLfPzKl1fcNM0eojvEErSdaBSDD1rdcJeBeefib-7yuVY9ALz5u7KgTR24aVniRsMym2M4xve6kIIO_-epdQ=w1960-h3486)
  
