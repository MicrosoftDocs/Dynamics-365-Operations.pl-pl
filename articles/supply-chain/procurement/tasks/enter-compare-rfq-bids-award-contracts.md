---
title: Wprowadzanie i porównywanie ofert dla ZO oraz udzielanie zamówień
description: W tym temacie pokazano sposób wprowadzania odpowiedzi na ZO, oceniania i porównywania ofert, a następnie zawierania umowy z jednym z dostawców.
author: mkirknel
manager: tfehr
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchRFQCaseTableListPage, PurchRFQCaseTable, PurchRFQReplyTable, PurchRFQCompare, PurchRFQEditLines, PurchRFQEditLinesParameters, PurchTable, PurchTablePart, PurchRFQCompareLinePrices, PurchRFQCompareRFQ
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ae7c43516fc90224439f6f7cfd5fd0a6058e8b39
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018429"
---
# <a name="enter-and-compare-rfq-bids-and-award-contracts"></a>Wprowadzanie i porównywanie ofert dla ZO oraz udzielanie zamówień

[!include [banner](../../includes/banner.md)]

W tym temacie pokazano sposób wprowadzania odpowiedzi na ZO, oceniania i porównywania ofert, a następnie zawierania umowy z jednym z dostawców. Procedurę można wykonać przy użyciu danych firmy demonstracyjnej **USMF**.

Przed rozpoczęciem trzeba mieć ZO z dwoma wierszami, które zostało wysłane co najmniej do dwóch dostawców. Aby utworzyć to ZO, wykonaj procedurę [tworzenia zapytania ofertowego](create-request-quotation.md). Przed wykonaniem tej procedury należy skonfigurować kryteria punktowania.

Ofertę można wprowadzić albo jako dostawca, albo jako pracownik działu zaopatrzenia. Aby uzyskać więcej informacji, zobacz temat [Konfigurowanie i obsługa współpracy z dostawcami](../set-up-maintain-vendor-collaboration.md).

## <a name="enter-a-reply-as-a-vendor"></a>Wprowadzanie odpowiedzi jako dostawca

1. Na pulpicie nawigacyjnym wybierz **Składanie ofert przez dostawców**.
2. Na liście **Nowe zaproszenia do składania ofert** znajdź ZO, które zostało właśnie wysłane. Wybierz ZO, aby sprawdzić, jakie były wymagania.
3. Wybierz **Załączniki ZO** w celu przejrzenia dodanych załączników.
4. Wybierz **Oferta** , aby włączyć opcję edycji pól. Zauważ, że pole **Oferta w toku** jest ustawione jako **Dostawca aktualizuje**.
5. W nagłówku i w wierszach wprowadź wartości z odpowiedzi na ofertę.
6. Jeśli do oferty mają zostać dodane jakiekolwiek załączniki, wybierz opcję **Załączniki ofert**.
7. Wybierz skróconą kartę **Wytyczne do przetargu** , aby sprawdzić, czy są wymagane jakieś dokumenty.
8. Otwórz skróconą kartę **Poprawki** , aby sprawdzić, czy ZO zostało zmienione.
9. Otwórz skróconą kartę **Kwestionariusz**. Należy odpowiedzieć na wszystkie wyświetlane w tym miejscu kwestionariusze
10. Otwórz skróconą kartę **Szczegóły wiersza** , aby wyświetlić rozszerzone informacje o wierszu.
11. Wybierz **Resetuj na podstawie ZO** tylko wtedy, gdy musisz zresetować wartości wprowadzone w pierwotnych wartościach ZO.
12. Ofertę można zapisać w dowolnym momencie i później wykonać dodatkowe przetwarzanie, pod warunkiem że data i godzina wygaśnięcia nie minęły. W takim przypadku ofertę można znaleźć na liście **oferty w toku** w obszarze roboczym **Składanie ofert przez dostawców**.
13. Gdy oferta jest gotowa do wysłania, wybierz opcję **Prześlij**. Jeśli nie chcesz składać oferty, wybierz opcję **Odrzuć**. Przesłane oferty są dostępne na liście **przesłanych ofert** w obszarze roboczym **Składanie ofert przez dostawców**.  
14. Po przesłaniu oferty można ją odwołać w dowolnym momencie przed datą i godziną wygaśnięcia. Należy pamiętać, że po wycofaniu oferty nie jest ona traktowana jako przesłana. Gdy oferta zostanie zaakceptowana lub odrzucona przez dział zaopatrzenia, będzie widoczna na liście **Wybrane oferty** lub **Przegrane oferty** w obszarze roboczym **Składanie ofert przez dostawców**.  

## <a name="enter-a-reply-from-a-vendor-as-a-procurement-professional"></a>Wprowadź odpowiedź od dostawcy jako pracownik działu zaopatrzenia

1. Upewnij się, że jest skonfigurowane uprawnienie do edytowania ofert dostawców. Przejdź do **Zaopatrzenie i sourcing \> ustawień \> Parametry modułu Zaopatrzenie i sourcing**. Na karcie **zapytanie ofertowe** ustaw opcję **Nabywca może edytować ofertę dostawcy** jako **Tak**.
2. Wybierz kolejno opcje **Zaopatrzenie i sourcing \> Zapytania ofertowe \> Wszystkie zapytania ofertowe**.
3. Zaznacz ZO o stanie **Wysłane** , a następnie kliknij łącze w polu **Sprawa dotycząca zapytania ofertowego**.
4. Wybierz **Zarządzaj odpowiedziami**. Na wyświetlonej stronie jest widoczna informacja o ZO dla każdego dostawcy, który został zaproszony do składania ofert.
5. Wybierz ZO, na które nie udzielono odpowiedzi. (Pole **Postęp odpowiedzi** powinno zostać ustawione jako **Nierozpoczęte**.)
6. Wybierz **Edycja \> Edytuj odpowiedź na ZO**. Zostanie wyświetlona strona **Odpowiedź na ZO**. Jako pracownik działu zaopatrzenia możesz teraz wprowadzić odpowiedź w imieniu dostawcy. Zauważ, że pole **Oferta w toku** jest ustawione jako **Nabywca aktualizuje**.  
7. Wprowadź dane ofertowe. Po zakończeniu wybierz przycisk **Prześlij**.

## <a name="score-the-bids"></a>Ocenianie ofert

1. Na stronie **Wszystkie zapytania ofertowe** wybierz sprawę ZO, dla której chcesz ocenić odpowiedzi.
2. Wybierz **Zarządzaj odpowiedziami**.
3. Wybierz opcję Odpowiedz na wynik.
4. Wybierz **nagłówek** , aby wyświetlić ocenę oferty.
5. Na skróconej karcie **Punktowanie oferty** wprowadź liczbę w polu **Wynik** dla jednego z kryteriów punktowania. Po umieszczeniu wskaźnika myszy nad jednym z kryteriów punktowania pojawia się etykietka narzędzia pokazująca zakres punktów, w którym trzeba się zmieścić. W tej demonstracji można podać liczbę z zakresu od 1 do 5 do każdego z kryteriów.  
6. Powtórz krok 5 dla innego kryterium określania wyników.
7. Jeśli sprawa ZO zawiera kwestionariusz, który został wysłany do dostawców, można wprowadzić ich odpowiedzi w na skróconej karcie **kwestionariuszy**.
8. Zamknij stronę.
9. Powtórz kroki od 1 do 8 dla wszystkich pozostałych ofert.

## <a name="compare-the-replies"></a>Porównywanie odpowiedzi

1. W okienku akcji na karcie **Ogólne** wybierz opcję **Porównaj odpowiedzi**.
2. W polu **Ranga** wprowadź liczbę.  
    - Ta strona pokazuje oferty z nagłówkami i informacjami w wierszach oraz łączny wynik punktowy na poziomie nagłówka. Wiersze można porównywać poprzez sortowanie ich w siatce, tak aby porównywalne wiersze znalazły się obok siebie. Podane są również następujące informacje:
    - **Ilość** : wielkości podane przez dostawcę. Ta ilość może nie być równa ilości określonej w ZO.
    - **Kwota netto** : Cena wskazana przez dostawcę, po odjęciu rabatów dla towarów w wierszu.
    - **Odchylenie** : Liczba dni różnicy między datą dostawy w ofercie lub wierszu a wymaganą datą dostawy w nagłówku lub wierszu zapytania ofertowego. Dla każdej oferty można wprowadzić rangę.  
3. Zaznacz wiersz nagłówka dla drugiej oferty, którą chcesz sklasyfikować.
4. W polu **Ranga** wprowadź liczbę.
5. Wybierz opcję **Zapisz**.

## <a name="reject-a-bid"></a>Odrzucanie oferty

1. Zaznacz wiersz nagłówka dla oferty, którą odrzucić. Można zaakceptować, odrzucić albo zwrócić tylko jedną ofertę lub wiersz jednej oferty na raz.
2. Zaznacz pole wyboru **Zaznacz.**  
    - Zaznaczenie pola wyboru **Zaznacz** w nagłówku oferty spowoduje oznaczenie również wszystkich wierszy. Aby odrzucić lub zaakceptować tylko niektóre wiersze oferty, można oznaczyć tylko te wiersze. Ponadto można zaakceptować oferty jednego dostawcy dla niektórych wierszy ZO, ale nagrodzić pozostałe wiersze ZO innego dostawcy. Należy jednak przetwarzać jedną ofertę na raz.  
    - Jeśli istnieją wiersze alternatywne, można zaakceptować oryginalny wiersz oferty lub jego alternatywę, ale nie oba.  
3. Wybierz opcję **Odrzuć**.
4. Wybierz **parametry** , a następnie w polu **Przyczyna odrzucenia** wprowadź lub wybierz przyczynę odrzucenia oferty. Przyczyna jest przechowywana w odpowiedzi.  
5. Kliknij przycisk **OK**.
6. Kliknij przycisk **OK**.

## <a name="accept-a-bid"></a>Akceptowanie oferty

1. Wybierz ofertę, którą chcesz zaakceptować, a następnie kliknij łącze w polu **Zapytanie ofertowe**. Jeśli znajdujesz się na stronie **porównywanie odpowiedzi na zapytanie ofertowe** , podświetlona oferta jest ofertą, którą system uwzględni w trakcie akcji „Akceptuj”. W danej chwili można akceptować wiersze tylko z jednej oferty.  
2. W okienku akcji kliknij pozycję **Odpowiedz**.
3. Wybierz **Akceptuj**. W przypadku zaznaczenia tylko określonych wierszy akcja Akceptuj spowoduje uwzględnienie tylko tych wierszy. Jeśli chcesz zaakceptować wszystkie wiersze oferty, nie musisz ich zaznaczać.  
4. Wybierz **parametry** , a następnie w polu **Przyczyna akceptacji** wprowadź lub wybierz przyczynę zaakceptowania oferty. Przyczyna jest przechowywana w ofercie.  
5. Kliknij przycisk **OK**.
6. Kliknij przycisk **OK**. Po kliknięciu przycisku **OK** zostanie wygenerowane zamówienie zakupu na podstawie wierszy objętych akceptacją ZO. Jeśli istnieją inne oferty, które nie zostały przetworzone (zaakceptowane, odrzucone lub zwrócone), system wyświetli monit o odrzucenie pozostałych ofert.  

## <a name="view-the-purchase-order-that-is-generated"></a>Wyświetlanie wygenerowanego zamówienia zakupu

W okienku akcji na karcie **Ogólne** wybierz opcję **Zamówienie zakupu**. Na wyświetlonej stronie widać zamówienie zakupu wygenerowane w momencie akceptacji oferty.
