---
title: Resetuj numery paragonów
description: W tym temacie opisano sposób resetowania numerów paragonów używanych dla różnych akcji w pożądanym dniu (na przykład rok obrachunkowy lub rok kalendarzowy).
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-Commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Commerce
ms.author: asharchw
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Application update 10.0.9
ms.openlocfilehash: f7242ed830d09a29a4b01e20ce5070c3aaeca62b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979728"
---
# <a name="reset-receipt-numbers"></a>Resetowanie numerów paragonów 

[!include [banner](includes/banner.md)]

> [!NOTE]
> Przed użyciem tej funkcji wymagane jest wybranie właściwości **Sekwencji niezależnej** dla wszystkich typów paragonów w profilu funkcji. Ponadto systemowa strefa czasowa urządzenia, w którym jest używany punkt sprzedaży, powinna być zgodna z odpowiednią strefą czasową magazynowania. Ze względu na te ograniczenia zaleca się, aby nie korzystać z tej funkcji w produkcji. Rozwiążemy te problemy w przyszłym wydaniu. 

Detaliści generują numery paragonów dla różnych akcji w sklepie, takich jak transakcje pieniężne i przeniesienia, transakcje zwrotu, zamówienia odbiorcy, oferty i płatności. Chociaż detaliści definiują własne formaty paragonów, w niektórych krajach lub regionach obowiązują przepisy nakładające ograniczenia dotyczące tych formatów paragonów. Na przykład te rozporządzenia mogą ograniczać liczbę znaków na paragonie, wymagać kolejnych numerów paragonów, ograniczać niektóre znaki specjalne lub wymagać resetowania numerów paragonów na początku roku. Microsoft Dynamics 365 Commerce oferuje bardzo elastyczny proces zarządzania numerami paragonów, aby ułatwić detalistom spełnienie wymagań prawnych. W tym temacie opisano sposób korzystania z funkcji resetowania numerów paragonów.

W module Commerce formaty paragonów mogą być alfanumeryczne. Można umieścić w nich zarówno zawartość statyczną, jak i zawartość dynamiczną. Zawartość statyczna zawiera literę, cyfry i znaki specjalne. Zawartość dynamiczna zawiera jeden lub więcej znaków reprezentujących informacje, jak numer sklepu, numer terminalu, Data, miesiąc, rok i sekwencje numerów, które są automatycznie zwiększane. Formaty są definiowane w sekcji **numeracja paragonów** profilu funkcji. W poniższej tabeli opisano znaki reprezentujące zawartość dynamiczną.

| Znaki | Opis |
|------------|-------------|
| N          | Znak **S** jest używany dla numeru sklepu. Jeśli na przykład sklep jest numerowany HOUSTON1, na paragonie w formacie **SSS** zostanie wyświetlona wartość „ON1”. Format **sssss** pokazuje na paragonie wartość „STON1”. |
| N          | Znak **T** jest używany dla numeru terminala. Jeśli na przykład terminal jest numerowany 0001, na paragonie w formacie **TTTT** zostanie wyświetlona wartość „0001”. |
| F          | Znak **C** jest używany dla numeru identyfikatora personelu. Jeśli na przykład pracownik ma identyfikator 000160, w paragonie w formacie **CCCC** zostanie wyświetlona wartość „0160”. |
| ddd        | Znaki **ddd** odpowiadają dniu roku, od 1 do 366. Na przykład dla 15 stycznia format **DDD** powoduje wyświetlenie na paragonie „015”. |
| MM         | Znaki **MM** są używane dla dwóch cyfr miesiąca. Na przykład dla stycznia format **MM** powoduje wyświetlenie na paragonie „01”. |
| DD         | Znaki **DD** są używane dla dwóch cyfr dnia miesiąca. Na przykład dla 15 stycznia format **DD** powoduje wyświetlenie na paragonie „15”. |
| RR         | Znaki **RR** są używane dla dwóch cyfr roku. Na przykład w dowolnym miesiącu w roku 2020 w formacie **RR** w paragonie zostanie wyświetlona wartość „20”. |
| \#         | Do sekwencyjnego numerowania jest używany znak numeru (**\#**). Na przykład format **####** powoduje wyświetlenie na paragonie „0001”, „0002”, „0003”. |

Można zresetować kolejne numerowanie paragonu w określonym dniu. Następnie w przypadku pierwszej transakcji po godzinie 00:00 w wybranej dacie wyzerowania system zresetuje sekwencję numerów paragonu do wartości 1. Można również określić, czy Resetowanie występuje tylko raz, czy powtarza się co rok. Jeśli określono Cykl roczny, Reset automatycznie przypada w każdym roku, dopóki sprzedawca nie zdecyduje się go zatrzymać. 

Aby włączyć reset, należy wykonać następujące kroki.

1. Wybierz kolejno opcje **Handel detaliczny i inny \> Ustawienia kanału \> Ustawienia punktu sprzedaży \> Profile punktów sprzedaży \> Profile funkcji**.
1. Na skróconej karcie **numeracji paragonów** wybierz opcję **Resetuj datę resetowania numeru**.
1. W oknie dialogowym rozwijanym w polu **Data resetowania** wybierz przyszłą datę wystąpienia resetowania.
1. W polu **Resetuj typ paragonu** wybierz **tylko jeden raz** lub **Corocznie**.
1. Kliknij przycisk **OK**.

![Wybieranie daty resetowania paragonu](media/Enable_receipt_reset.png "Wybieranie daty resetowania paragonu")

Po wybraniu daty zostanie ona wyświetlona w kolumnie **Data następnego resetowania numeru paragonu**. Data resetowania jest stosowana do wszystkich typów transakcji paragonów. W związku z tym sekwencja numerów paragonów zostanie zresetowana dla wszystkich typów paragonów.

Po nadejściu daty resetowania Numer paragonu jest resetowany dla pierwszej transakcji każdego typu. Ponadto w profilu funkcji Data resetowania jest przenoszona z kolumny **Data następnego resetowania numeru paragonu** do kolumny **Data bieżącego resetowania numery paragonu**. Ta zmiana wskazuje, że jeśli rejestr nie jest używany w dniu resetowania, Numer paragonu zostanie zresetowany przy kolejnym *użyciu* tego rejestru. Na przykład w dniu 3 grudnia 2019 jako datę resetowania zostanie wybrana opcja **1 stycznia 2020**. 1 stycznia, gdy kasa dokonuje pierwszej transakcji, Numer paragonu jest resetowany. Jednak jedna kasa nie jest używana w grudniu i styczniu, a pierwsze jej użycie zaczyna się w lutym. W takim przypadku, ponieważ zdefiniowano akcję resetowania, Numer paragonu w tym rejestrze zostanie zresetowany, gdy zarejestruje swoją pierwszą transakcję w lutym.

Aby wyczyścić przyszłe daty resetowania, można skorzystać z funkcji **czyszczenia dat resetowania**. Jeśli jednak Data resetowania wystąpiła w przeszłości, nie można jej cofnąć. W związku z tym Reset będzie nadal występował dla wszystkich Kas, w których nie nastąpiły jeszcze Resetowanie.

> [!NOTE]
> W zależności od wybranej daty wyzerowania i formatu paragonu mogą istnieć zduplikowane numery paragonów. Mimo że system punktu sprzedaży (POS) może obsłużyć te sytuacje, zwiększa się czas wymagany do przetworzenia zwrotów, ponieważ klienci z jednostkami sprzedażowymi muszą wybierać spośród zduplikowanych przyjęć. Inne komplikacje związane z oczyszczaniem danych mogą wystąpić, jeśli duplikaty paragonów nie zostały zaplanowane. Z tego względu zaleca się stosowanie dynamicznych znaków daty (na przykład **DDD**, **mm**, **DD** i **RR**) w celu uniknięcia zduplikowanych numerów paragonów po wyzerowaniu.


[!INCLUDE[footer-include](../includes/footer-banner.md)]