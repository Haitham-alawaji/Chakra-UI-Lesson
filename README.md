# Chakra UI-Lesson
![Chakra UI](https://raw.githubusercontent.com/chakra-ui/chakra-ui/main/media/logo-colored@2x.png?raw=true)

# سوف نتعلم في هذا الدرس :

* التعرف على مكتبة  Chakra UI
* إضافة ChakraUI للمشروع 
* تخصيص عناصر من ChakraUI


# مقدمة عن Chakra UI :


  مكتبة الـ[Chakra UI](https://www.google.com) هي مكتبة محتوى (component librire)  خاصة في تنسيق العناصر وهي تعمل مع أكثر من إطار عمل (framework) مثل :  Next.js ,Gatsby والاهم بالنسة للهذا الدرس هو React.js. 
  
  حيث تتكون مكتبة ChakraUI من عناصر جاهزةللإدراج في المشروع وقابلة للتعديل و التخصيص للتناسب العمل ومتطلباته 
  # مايميز Chakra UI :
  *  قابل للتخصيص بالكامل : تتيح للمستخدم الحرية الكاملة في التعديل على كامل خصائص العنصر مثل الحجم اللون الخط وغيره .
  * متكيفة\Responsive : جميع العناصر في مكتبة ChakraUI متكيفة (Responsive) مع مختلف أحجام شاشات العرض.
  * دعم TypeSeript 
  * مكتبة جديدة و في تحديث مستمر 
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
أو يمكن تغير اللون من خلال خصائص العنص `prop` مثل :
```js
      <Text
            mt="1"
            fontWeight="semibold"
            as="h4"
            lineHeight="tight"
            noOfLines={1}
            color='#fff'
          >
            Hello word!
          </Text>
```
## خضائص /props
تستعمل ChakraUI خصائص مقاربة للخصائص الموجود في `CSS` في الجدول التالي يوضح اكثر الخصائص المستعملة :
| ChakraUI    | CSS         | prop      |
| ----------- | ----------- | --------- |
| m, margin	  | margin      |           |
| color       | color       |           |
|             |             |           |
