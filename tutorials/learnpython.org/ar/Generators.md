المولدات سهلة جداً في التنفيذ، لكنها صعبة الفهم بعض الشيء.

تُستخدم المولدات لإنشاء المُكررات، لكن بنهج مختلف. المولدات هي وظائف بسيطة تعيد مجموعة قابلة للتكرار من العناصر، واحدة تلو الأخرى، بطريقة خاصة.

عند البدء في التكرار على مجموعة من العناصر باستخدام عبارة for، يتم تشغيل المولد. بمجرد أن يصل رمز وظيفة المولد إلى عبارة "yield"، يقوم المولد بإعادة التنفيذ إلى حلقة for، مع إعادة قيمة جديدة من المجموعة. يمكن لوظيفة المولد أن تولد عددًا من القيم (وربما لانهائية) بقدر ما تريد، مع توليد كل واحدة منها في دورها.

فيما يلي مثال بسيط لوظيفة مولد تعيد 7 أرقام صحيحة عشوائية:

      import random
      
      def lottery():
          # يعود بـ 6 أرقام بين 1 و40
          for i in range(6):
              yield random.randint(1, 40)
      
          # يعود برقم سابع بين 1 و15
          yield random.randint(1, 15)
      
      for random_number in lottery():
             print("And the next number is... %d!" %(random_number))

تقرر هذه الوظيفة كيفية توليد الأرقام العشوائية من تلقاء نفسها، وتنفذ عبارات yield واحدة تلو الأخرى، بين كل yield تتوقف لتعيد التنفيذ إلى حلقة for الرئيسية.

تمرين
--------

اكتب وظيفة مولد تعيد سلسلة فيبوناتشي. يتم حسابها باستخدام الصيغة التالية: الرقمين الأولين من السلسلة يساويان دائماً 1، وكل رقم لاحق يتم إعادته هو مجموع آخر رقمين.
تلميح: هل يمكنك استخدام متغيرين فقط في وظيفة المولد؟ تذكر أنه يمكن القيام بالتعيينات بشكل متزامن. الكود

    a = 1
    b = 2
    a, b = b, a
    print(a, b)

سيقوم بتبديل قيم a و b في نفس الوقت.