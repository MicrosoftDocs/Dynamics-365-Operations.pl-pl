---
title: "Sprzedaż i marketing"
description: "Moduł Sprzedaż i marketing umożliwia pozyskiwanie, przechowywanie i wykorzystywanie różnego rodzaju danych w procesie sprzedaży. Te dane obejmują pierwotną akcję handlową, przyszłe działanie uzupełniające oraz dodatkowe transakcje sprzedaży."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 92303
ms.assetid: 65ca9992-bbfa-4224-bf0e-067a25c7e6a4
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 25ea6e64453b22d664dd65a1f1bb18e3a1997bc5
ms.contentlocale: pl-pl
ms.lasthandoff: 05/25/2017


---

# <a name="sales-and-marketing"></a>Sprzedaż i marketing

[!include[banner](../includes/banner.md)]


Moduł Sprzedaż i marketing umożliwia pozyskiwanie, przechowywanie i wykorzystywanie różnego rodzaju danych w procesie sprzedaży. Te dane obejmują pierwotną akcję handlową, przyszłe działanie uzupełniające oraz dodatkowe transakcje sprzedaży.

<a name="marketing"></a>Marketing
---------

Kampanie i działania marketingowe umożliwiają wyszukiwanie potencjalnych klientów i budowanie z nimi relacji, tak aby początkowe interakcje przekształciły się w relacje sprzedażowe. Poniższy schemat procesu ilustruje proces biznesowy marketingu. [![Proces biznesowy marketingu](./media/marketing01.jpg)](./media/marketing01.jpg)

### <a name="relationships"></a>Relacje

W sprzedaży i marketingu początkowe interakcje z potencjalnymi klientami mogą występować w różnych sytuacjach. Może na przykład znaleźć potencjalnego klienta podczas udziału w targach handlowych albo potencjalnego leada sprzedażowego po przeprowadzeniu przez firmę kampanii wykorzystującej korespondencję seryjną. To bardzo ważne, aby zrozumieć przebieg procesów w organizacji podmiotu, zanim stanie się on klientem. Na poniższym rysunku przedstawiono procesy, jakie mogą wystąpić w jednostkach organizacji, zanim z potencjalnego klienta przeistoczy się ona w faktycznego klienta. [![SalesandMarketing01](./media/salesandmarketing01.jpg)](./media/salesandmarketing01.jpg)

### <a name="campaigns"></a>Kampanie

Celem kampanii są osoby kontaktowe u potencjalnych klientów, leadów sprzedażowych, szans sprzedaży i istniejących klientów, których wybrano do udziału w kampanii. W programie Microsoft Dynamics 365 for Operations można utworzyć kilka typów kampanii, np. telemarketingowe, wykorzystujące korespondencję seryjną i wykorzystujące pocztę e-mail, aby zmaksymalizować spodziewane korzyści z klienta. Wraz z postępem kampanii i notowaniem pozytywnych reakcji można rozpocząć proces sprzedaży wobec najlepiej rokujących adresatów.

## <a name="sales"></a>Sprzedaż
Funkcje sprzedaży umożliwiają tworzenie ofert, sprzedaż dodatkową i powiązaną nowym i istniejącym klientom, tworzenie zamówień sprzedaży oraz tworzenie faktur sprzedaży dla odbiorców. Poniższy schemat procesu ilustruje proces biznesowy sprzedaży. [![Proces biznesowy sprzedaży](./media/sales01.jpg)](./media/sales01.jpg)

### <a name="sales-quotations"></a>Oferty sprzedaży

Oferty sprzedaży tworzy się w celu przedstawienia odbiorcom oferty na towary lub usługi, które firma będzie dostarczać. Klient może zażądać oferty lub też można utworzyć ofertę w odpowiedzi na prośbę potencjalnego albo istniejącego klienta. Gdy klient zaakceptuje ofertę sprzedaży, można ją przekształcić na zamówienie sprzedaży.

### <a name="up-sellcross-sell"></a>Sprzedaż dodatkowa/powiązana

Sprzedaż dodatkowa i powiązana to techniki sprzedaży produktów stosowane podczas wprowadzania zamówienia od klienta. W sprzedaży dodatkowej produkt jest proponowany zamiast bieżącego produktu. W sprzedaży powiązanej produkt jest proponowany w uzupełnieniu bieżącego produktu. Po skonfigurowaniu list produktów można tworzyć konkretne reguły wskazujące, kiedy dany produkt powinien być sugerowany jako powiązany lub dodatkowy.

### <a name="sales-orders"></a>Zamówienia sprzedaży

Podczas tworzenia nowego zamówienia sprzedaży należy wybrać jego typ. Masz do wyboru pięć opcji. **Uwaga:** Po utworzeniu każdego zamówienia sprzedaży można zmienić jego typ, z wyjątkiem zamówienia typu **Zapotrzebowanie na pozycje**, jeśli zamówienie ma stan **Dostarczone**.

| Typ zamówienia sprzedaży  | Opis                                                                                                                                                                                                                                                                                            |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| W arkuszu           | Użyj tego typu jako wersji roboczej dla zamówienia sprzedaży. Ten typ nie ma wpływu na ilości zapasów i nie powoduje generowania transakcji towarowych.                                                                                                                                                                    |
| Subskrypcja      | Używaj tego typu dla zamówień cyklicznych. Podczas fakturowaniu zamówienia jego stan jest automatycznie ustawiany na zamówienie otwarte. Następuje aktualizacja informacji o zafakturowanej ilości dostarczonej i pozostałych dostawach. Tego typu zamówienia sprzedaży nie można użyć, jeśli są używane funkcje modułu Zarządzanie magazynem. |
| Zamówienie sprzedaży       | Użyj tego typu, gdy klient złożył lub potwierdził zamówienie.                                                                                                                                                                                                                                        |
| Zwrot towaru    | Użyj tego typu, gdy klient zwraca towar. Numer zwrotu towaru (numer RMA) jest przypisywany automatycznie.                                                                                                                                                                                            |
| Zapotrzebowanie na pozycje | Ten typ jest tworzony automatycznie po sprzedaży towaru za pośrednictwem projektu.                                                                                                                                                                                                                       |

### <a name="sales-agreements"></a>Umowy sprzedaży

Umowa sprzedaży jest kontraktem, który zobowiązuje odbiorcę do zakupu produktu w określonej ilości lub za określoną kwotę w ustalonym czasie w zamian za specjalne ceny i rabaty. Ceny i rabaty w umowie sprzedaży zastępują ceny i rabaty, które są określone w jakichkolwiek istniejących umowach handlowych. Umowa sprzedaży jest ważna przez ustalony okres. Żądana data wysyłki określona dla sprzedaży na stronie **Zamówienie sprzedaży** powinna się mieścić w okresie ważności. Domyślnie umowa zakupu jest wstrzymana. Na podstawie umowy sprzedaży można zamawiać tylko wtedy, gdy jest ona ustawiona jako **Obowiązuje**.

### <a name="backorders"></a>Zamówienia niezrealizowane

Podczas wprowadzania zamówień i sprawdzania ich poprawności może wystąpić konieczność zarządzania zamówieniami niezrealizowanymi i wyjątkami, zanim będzie możliwa realizacja sprzedaży. Zamówienia niezrealizowane są albo zamówieniami zakupu, które nie zostały jeszcze dostarczone od dostawcy, lub zamówieniami sprzedaży, które nie zostały jeszcze dostarczone do odbiorcy. Bardzo ważne jest, aby nie pozostawiać zamówień niezrealizowanych. Przykładowo jeśli dostawa produktów od dostawcy opóźnia się, może być konieczna zmiana daty dostawy do odbiorcy, a następnie poinformowanie odbiorcy o opóźnieniu. Niezrealizowanych zamówienia można wyświetlać według towaru (pozycji), odbiorcy lub dostawcy.

#### <a name="viewing-backorders-by-item"></a>Wyświetlanie niezrealizowanych zamówień wg towaru

Przeglądając niezrealizowane zamówienia według towaru, można odpowiednio zareagować na oczekiwany przyszły przepływ transakcji dotyczących określonego towaru. Na przykład można sprawdzić następujące informacje:

-   Liczba zamówień sprzedaży złożonych na towar.
-   Czy dostawy towaru od dostawców są nadal niezrealizowane.
-   Czy należy zamówić więcej towaru, tak aby dostawy dla wszystkich zamówień sprzedaży można było wykonać w terminie.

Dzięki temu sprawdzeniu można odpowiadać na pytania klientów o czas dostawy towaru. Ponadto istnieje możliwość ustalania priorytetów niezrealizowanych zamówień sprzedaży oraz podziału dostępnych towarów między zamówienia.

#### <a name="viewing-backorders-by-customer"></a>Wyświetlanie niezrealizowanych zamówień wg odbiorcy

Wyświetlając niezrealizowane zamówienia według odbiorcy, można obejrzeć stan pozostałych zamówień odbiorcy. To sprawdzenie jest przydatne, gdy trzeba odpowiedzieć odbiorcom oczekującym na opóźnione towary.

#### <a name="viewing-backorders-by-vendor"></a>Wyświetlanie niezrealizowanych zamówień wg dostawcy

Wyświetlając niezrealizowane zamówienia według dostawcy, można interweniować w sytuacjach braku dostaw i ryzyka niedotrzymania oczekiwanych dat dostaw. To sprawdzenie pomaga także określić priorytet niezrealizowanych zamówień w sytuacji, gdy produkty nadejdą od dostawców i trzeba je pobrać dla zamówień sprzedaży w celu dostawy.

### <a name="invoices"></a>Faktury

W trakcie procesu sprzedaży można tworzyć trzy typy faktur:

-   Faktura dla odbiorcy
-   Faktura niezależna
-   Faktura VAT pro-forma

#### <a name="customer-invoice"></a>Faktura dla odbiorcy

Faktura dla odbiorcy to dokument rachunkowy wystawiany przez organizację odbiorcy w związku ze sprzedażą. Tworzy się ją na podstawie zamówienia sprzedaży zawierającego nagłówek oraz jeden lub więcej wierszy dla towarów lub usług. Faktura dla odbiorcy finalizuje zamówienie sprzedaży, dokument dostawy i cykl faktury sprzedaży.  

Można zaksięgować i wydrukować pojedynczą fakturę dla odbiorcy na podstawie zamówienia sprzedaży lub dokumentu dostawy i daty. Można także zaksięgować i wydrukować wiele faktur dla odbiorców razem na podstawie dokumentów dostawy i dat. Podczas księgowania jednej faktury dla odbiorcy na podstawie zamówienia sprzedaży ilość **Pozostałe do zafakturowania** dla każdej pozycji jest aktualizowana według sumy wszystkich zafakturowanych ilości z wybranego zamówienia sprzedaży.  

Jeśli ilości w polach wartości **Pozostałe do zafakturowania** i **Pozostałe do dostarczenia** dla wszystkich towarów z zamówienia sprzedaży są zerowe, zamówienie sprzedaży otrzymuje stan **Zafakturowane**. Jeśli wartość w którymkolwiek polu nie jest zerowa, stan zamówienia sprzedaży nie jest modyfikowany i można wprowadzać dodatkowe faktury. Jeśli masz zamiar zaksięgować i wydrukować jedną lub więcej faktur dla odbiorców na podstawie dokumentów dostawy, musi już być zaksięgowany co najmniej jeden dokument dostawy dla każdego zamówienia sprzedaży. Faktura dla odbiorcy jest oparta na dokumentach dostawy i odzwierciedla figurujące w nich ilości.  

Fakturę dla odbiorcy opartą na pozycjach wierszy dokumentu dostawy, które dotąd wysłano, można utworzyć nawet jeśli wszystkie pozycje dla danego zamówienia sprzedaży nie zostały jeszcze wysłane. Można tak uczynić, jeśli na przykład co miesiąc firma wystawia każdemu odbiorcy fakturę wyszczególniającą wszystkie dostawy zrealizowane w danym miesiącu. Każdy dokument dostawy odpowiada częściowej lub kompletnej dostawie towarów ujętych w zamówieniu sprzedaży.  

Po zaksięgowaniu faktury wartość **Pozostałe do zafakturowania** jest dla każdego towaru aktualizowana z uwzględnieniem całości dostaw w ramach wybranych dokumentów dostawy. Jeśli ilości w polach wartości **Pozostałe do zafakturowania** i **Pozostałe do dostarczenia** dla wszystkich towarów z zamówienia sprzedaży są zerowe, zamówienie sprzedaży otrzymuje stan **Zafakturowane**. Jeśli wartość nie jest zerowa, stan zamówienia sprzedaży nie jest modyfikowany i można wprowadzać dodatkowe faktury. Transakcje magazynowe są aktualizowane o numer faktury, a stan wiersza zamówienia sprzedaży zmienia się na **Zafakturowane**.

#### <a name="free-text-invoice"></a>Faktura niezależna

Faktura niezależna to faktura, która nie ma powiązania z zamówieniem sprzedaży. Zawiera wiersze zamówienia z kontami księgowymi, tekstowymi opisami i kwotą sprzedaży. W tego rodzaju fakturze nie można wprowadzić numeru towaru oraz należy wpisać odpowiednie dane podatku. W każdym wierszy faktury jest wskazane konto główne sprzedaży. Saldo odbiorcy jest księgowane na koncie rozrachunkowym określonym w profilu księgowania używanym dla faktury niezależnej.

#### <a name="pro-forma-invoice"></a>Faktura VAT pro-forma

Faktura pro forma to faktura przygotowana jako oszacowanie rzeczywistej kwoty faktury przed zaksięgowaniem faktury. Fakturę pro forma można wydrukować zarówno dla faktury dla odbiorcy, jak i dla faktury niezależnej.




