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
  * متكيفة\Responsive : جميع العناصر في مكتبة ChakraUI متكيفة (Responsive) مع مختلف أحجام شاشات العرض.
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
على عكس `css` جميع عناصر `chakra-ui` تبدأ بحرف كبير =========>
### box : 
يعد عنصر `Box` خلاصة جميع العناصر حيث يعد من العناصر الأساسية في بناء جميع العناصر الاخرى , ويحل محل `dev`
تكون أهمية إستعمال `Box` في
* تصميم واجهات متكيفه بسهولة 
* توفر إختصار من خلال تمرير `props` فا بدلا من إستعمال `backgroundColor` نستطيع إستعمال `bg` وتعطي نفس النتيجة 
* إستعمال خصائص عنصر اخر عن طريق `as` prop
```js
 <Box bg="#fff" as='button'>This is a card</Box>

```

خطواة إستعمال box
اولا : نستدعي `Box`من مكتبة `@chakara-ui/react`
```js
import { Box } from '@chakra-ui/react'

```





تقدم مكتبة ChakraUI عناصر جاهزة للاستخدام للتوفير الوقت ,وللإطلاع على جميع العناصر `Components` تفضل بزيارة الصفحةالخاصة بالخصائص `Components` في [Chakra UI](https://chakra-ui.com/docs/components)


## تخصيص السمة 
تتيح Chakra ui  القدرة الكامله على التعديل على السمة التصميم كا تغير الوضع الوضع النهار و الليلي والأللوان الخاصة بكل  منهما 
للاستفادة من هذه الميزة نضيف في ملف `index.tsx`الخاص في المشروع متغر `colors` بالطريقة التالية : 

```js

import { extendTheme, ChakraProvider } from '@chakra-ui/react'


const colors = {
  brand: {
    900: '#1a365d',
    800: '#153e75',
    700: '#2a69ac',
  },
}

```


أو يمكن تغير اللون من خلال خصائص العنصر `prop` مثل :
```js
      <Text
            color='#000000'
          >
            Hello word!
          </Text>
```
## خضائص /props
تستعمل ChakraUI خصائص مقاربة للخصائص الموجود في `CSS` في المثال التالي يوضح اكثر الخصائص المستعملة :
====================>
```js

<Text
                mt="1"
                dir='rtl'
                lang='ar'
                fontWeight="semibold"
                fontFamily='Caveat'
                lineHeight="tight"
                color='#000000'
              >
                Hello word!
              </Text>
```
* `mt` :
* `dir` :
* `lang`:
* `fontFamily` :
* `lineHeight` :
* `color` :


| ChakraUI    | CSS         |     
| ----------- | ----------- |
| m, margin	  | margin      |  
| color       | color       |
| bg, background     |   background       | 
|      fontFamily    |   font-family	    | 
|      fontSize      |  font-size	          | 



وللإطلاع على جميع الخصائص `props` تفضل بزيارة الصفحةالخاصة بالخصائص `props` في [Chakra UI](https://chakra-ui.com/docs/styled-system/style-props) 


## متكيفة\Responsive
يعتبر Responsive والتي تعني ان محتوى الصفحه يتماشى مع أي حجم شاشه ينعرض فيها (مثل: PC, smart phone).
```js
<Text fontSize={{ base: "24px", md: "40px", lg: "56px" }}>
 This is responsive text
</Text>
```
`base` 
, `md` 
, `lg`



 ## النماذج / Templates 
 يتميز ChakraUI بوجود نماذج جاهز للإضافة للمشروعك و تعديل عليها لكي تناسب مشروعك ,و  من اشهر هذه المواقع [chakra templates](https://chakra-templates.dev/) و, [choc-ui](https://choc-ui.com/) .
 ![Chakra UI](https://raw.gt.com/chakra-ui/chakra-ui/main/media/logo-colored@2x.png?raw=true)

`navbar` :
![Chakra UI](https://raw.usercontent.com/chakra-ui/chakra-ui/main/media/logo-colored@2x.png?raw=true)
```js

```
