---
title: "Omówienie zaopatrzenia i sourcingu"
description: "Ten artykuł zawiera omówienie funkcji dostępnych w module Zaopatrzenie i sourcing."
author: FrankDahl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 58021
ms.assetid: eea24e23-a803-4de0-a218-6485757cde1b
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 0692518afc5c8b385773dad3c44dc4e3c978362b
ms.contentlocale: pl-pl
ms.lasthandoff: 11/03/2017

---

# <a name="procurement-and-sourcing-overview"></a>Omówienie zaopatrzenia i sourcingu

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera omówienie funkcji dostępnych w module Zaopatrzenie i sourcing.

Zaopatrzenie i sourcing obejmują wszystkie etapy od identyfikacji popytu na produkty i usługi przez zakup produkty, odebranie, fakturowanie i przetwarzanie płatności z dostawcami. Procesy zaopatrzenia można skonfigurować według konkretnych potrzeb biznesowych, definiując zasady i przepływy pracy związane z zaopatrzeniem.

## <a name="identifying-a-need-for-product-and-services"></a>Identyfikowanie popytu na produkty i usługi
Popyt na produkty i usługi może wynika z *zapotrzebowania* — na przykład jeśli pracownik potrzebuje produktu. *Katalogi produktów* można skonfigurować w taki sposób, by wyświetlały podpowiedzi przy wyborze dostępnych produktów lub umożliwiały tworzenie żądań dla produktów, które nie są jeszcze dostępne w katalogu, dając działowi zaopatrzenia możliwość znalezienia sposobu, w jaki ten produkt może zostać dostarczony.  

*Limity wydatków* mogą służyć do ograniczania zapotrzebowania wydatków, a *przepływ pracy zaopatrzenia* pozwala dodać opcję żądania zatwierdzenia przed złożeniem zamówienia. Można też określić alokację środków budżetu, jeśli jest to wymagane.  
  
Dział zaopatrzenia identyfikuje dostawców dla wymaganych produktów i usług, i może to być związane z wysłaniem *zapytania ofertowego* do wielu potencjalnych dostawców. Istnieje możliwość udostępniania specyfikacji żądanego produktu i potencjalni dostawcy można je wyświetlić, jeśli są w stanie dostarczyć produkt, który jest z nimi zgodny. Dostawcy odsyłają oferty, a dział zaopatrzenia przegląda je i dokonuje ostatecznego wyboru dostawcy.  

Zamiast złożonego zapytania ofertowego w ramach zamówienia zakupu można wysłać do dostawcy *zapytanie dotyczące zakupu*. Pomaga ono w ustalaniu różnego rodzaju warunków, takich jak ceny, rabaty i data dostawcy dla zamówienia. Jeśli dostawcy mogą korzystać z portalu **Dostawca**, funkcja zapytań o zakupy jest wyłączona. Zamiast tego zamówienie jest udostępniane w portalu **Dostawca** i gdy *prośba o potwierdzenie* jest wysyłana, dostawca może bezpośrednio potwierdzić zamówienie.  

*Katalogi dostawcy* mogą być używane do zbierania informacji o asortymencie produktów, który dostawca może dostarczyć. Dostawcy mogą publikować własne katalogi, co ułatwia aktualizowanie oferty. Do produktu można dołączyć *listę zatwierdzonych dostawców* i może ona ułatwić w wyborze dostawcy podczas otwierania nowych zamówień zakupu i zapobiegać korzystaniu z usług niepożądanych dostawców.

## <a name="procurement"></a>Zaopatrzenie
*Zamówienia zakupu* można tworzyć na wiele różnych sposobów, w tym:

-   Jako wynik planowania głównego, które zostało zidentyfikowane jako popyt wymagający zakupu. Ten proces generuje planowane zamówienia zakupu, a kiedy te są zwalniane, generowane są zamówienia zakupu.
-   Przez przetworzenie zapotrzebowania na zakup, którego efektem jest zakup.
-   Przez przetwarzanie zamówienia zakupu, gdzie zamówienia zakupu są tworzone jako zamówienia zwolnienia z umów. Jest to powszechnie używane, gdy umowy zakupu służą za zamówienia zbiorcze.
-   Ręcznie, podczas utworzone zamówienie zakupu nie opiera się na innym dokumencie.

Zamówienia zakupu, które są skonfigurowane przy użyciu *przepływów pracy zakupów* wymagają zatwierdzenia przed zarejestrowaniem. Jest to konieczne do dalszego przetwarzania zamówienia.  

Zamówienia zakupu są *potwierdzane*, tak aby odzwierciedlały umowę zawartą z dostawcą. Zamówienia zakupu będą następnie stopniowo przetwarzane w różnych stanach, aż zostaną ostatecznie zafakturowane lub anulowane.  

Podczas tworzenia zamówienia zakupu wiele pól jest wstępnie uzupełnianych wartościami z domyślnych informacji o dostawcy przechowywanych na stronie **Dostawcy**. Oznacza to, że trzeba wypełnić tylko niektóre pola konieczne w zamówieniu zakupu, ale można też zamienić wprowadzone automatycznie wartości domyślne.

### <a name="prices-and-discounts"></a>Ceny i rabaty

Ceny i rabaty zawierają informacje o cenach, rabatach i warunkach rabatów. Ceny i rabaty mogą być takie jak w *umowie* *handlowej*. Umowy handlowe reprezentują cenniki dostawcy z cenami lub rabatami i mają określony zakres dat obowiązywania umowy. Ceny i rabaty można negocjować i zapisywać w *umowach zakupu* z warunkami, takimi jak zobowiązanie do zakupu określonej ilości towaru lub kwoty będące podstawą do negocjacji. Można utworzyć *Umowy rabatowe* z dostawcami i skonfigurować je tak, aby zamówienie określonych produktów lub grup produktów powodowało przyznanie rabatu zależnego od kwoty lub wielkości zamówienia.

### <a name="delivery-options"></a>Opcje dostawy

Dostępne są różne opcje dla procesu dostawy skojarzonego z zamówieniem zakupu. Zamówione produkty można podzielić na harmonogramy *dostaw*, w których części zamówionej ilości mogą zostać zaplanowane dla dostawy z różnymi datami. Można również uwzględnić dostawy *dostawę bezpośrednią* inicjowaną z poziomu zamówienia sprzedaży, który automatyzuje generowanie dokumentu dostawy na zamówieniu sprzedaży, w tym samym czasie, gdy dokument przyjęcia produktu jest rejestrowany w zamówieniu zakupu. Zamówienia zakupu mogą także być częścią łańcucha *zamówienia międzyfirmowego*, zwanego także międzyfirmowym zamówieniem zakupu, w którym produkty zamawia się z pasującego międzyfirmowego zamówienia sprzedaży. W takiej sytuacji niektóre kroki są wykonywane automatycznie między dwoma powiązanymi zamówieniami międzyfirmowymi.

### <a name="supplementary-items"></a>Pozycje dodatkowe

Produkty można ustawić tak, aby uwzględnić *towary dodatkowe*. Ma to na celu zaproponowanie produktów powiązanych z zamówionym towarem. Dodatkowe produkty mogą być wymagane lub mogą być opcjonalne. W niektórych przypadkach towary dodatkowe mogą być dodawane jako bezpłatne produkty do innych zamówionych produktów.

### <a name="purchase-order-charges"></a>Opłaty zamówienia zakupu

Do zamówienia zakupu można przypisać opłaty. Mogą one być przypisywane automatycznie poprzez konfigurację opłat automatycznych, ale można je również wprowadzać ręcznie. Opłaty mogą być przypisane do zamówienia na poziomie nagłówka lub wiersza. Księgowanie opłat można ustawić na różne sposoby. Można na przykład skonfigurować księgowanie opłaty jako kosztu produktu. W takim wypadku opłaty muszą być przypisane na poziomie wiersza zamówienia przed potwierdzeniem zamówienia. Istnieje możliwość alokacji opłat z nagłówka do wierszy zamówienia.

## <a name="product-receipt-and-invoicing"></a>Dokument przyjęcia produktów i fakturowanie
Zamówienia zakupu zawierające fizyczne produkty z reguły wymagają *rejestracji przyjęcia* w magazynie. Następnie dla zamówienia jest rejestrowany *dokument przyjęcia produktów*. Zamówienia zakupu z produktami, które spełniają zapotrzebowanie, można skonfigurować tak, aby pracownik, który zażądał produktów, musiał także dostarczyć *potwierdzenie przyjęcia*.  

Niektóre zamówienia zakupu zawierają produkty, które są usługami lub innymi produktami niefizycznymi, w przypadku których potwierdzenie przyjęcia do magazynu nie jest wymagane. Produkty mogą być tworzone jako usługi. Można też używać w zamówieniach zakupu bezpośrednio *kategorii zaopatrzenia*. W przypadku takich zamówień księgowanie dokumentów przyjęcia produktów jest czasem pomijane, a zamówienie jest fakturowane bezpośrednio. Czasami dokonuje się rejestracji dokumentu przyjęcia produktu bez żadnej wcześniejszej rejestracji jego odbioru.  

Przyjęcie produktów może spowodować automatyczne zużycie w określonym celu. Dotyczy to też domniemanego zużycia z bezpośrednią dostawą, zużycia w ramach projektu lub księgowania produktu jako środka trwałego.  

*Faktury od dostawcy* można najpierw zarejestrować w *rejestrze faktur* niezależnie od zamówienia zakupu, a następnie zatwierdzać je jako rekord względem zamówienia zakupu. Rejestrowanie faktur od dostawcy z zamówieniem zakupu obejmuje uzgadnianie dokumentu przyjęcia produktów z fakturą.  

Dla zamówienia zakupu można określić *Zasady podziału księgowań*, aby opisać sposób księgowania. Można także określić sposób uzyskiwania alokacji środków budżetu, o ile jest on uwzględniony w konfiguracji.  

Zafakturowane zamówienia zakupu zarejestruje zobowiązanie na koncie dostawcy w ramach rozrachunków z dostawcami i z tego miejsca będzie można przetworzyć ***płatność dostawcy*.

## <a name="vendor-performance"></a>Wydajność dostawcy
Wydajność i przegląd zakupów obsługują *raporty zaopatrzenia i rozrachunków z dostawcami,* które obejmują analizy wydatków i analizy wydajności dostawcy.




