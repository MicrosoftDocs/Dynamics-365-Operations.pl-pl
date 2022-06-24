---
title: Szczegóły transakcji inwentaryzacyjnej
description: Ten artykuł zawiera przegląd strony szczegółów transakcji, na stronie ze szczegółami wybranej transakcji magazynowej.
author: rachel-profitt
ms.date: 04/25/2022
ms.topic: article
ms.search.form: InventTrans, InventTransDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-04-25
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 55e29d5804f57cd86fb5ddac5d6c5576b7ea5f61
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859395"
---
# <a name="inventory-transaction-details"></a>Szczegóły transakcji inwentaryzacyjnej

Strona Szczegóły **transakcji umożliwia** wyświetlenie szczegółów wybranej transakcji magazynowej.

## <a name="open-the-transaction-details-page"></a>Otwórz stronę Szczegóły transakcji

Aby otworzyć stronę **Szczegóły transakcji**, wykonaj te czynności.

1. Wybierz kolejno opcje **Zarządzanie zapasami \> Zapytania i raporty \> Transakcje**.
1. Wybierz transakcję, którą chcesz sprawdzić.
1. W okienku akcji wybierz pozycję **Szczegóły transakcji**.

## <a name="fasttabs-overview"></a>Przegląd skróconych kart

Strona **szczegółów transakcji** jest dzielona na kilka skróconych kart. W poniższej tabeli opisano przeznaczenie każdej skróconej karty.

| Skrócona karta | Opis |
|---|---|
| Ogólny | Na tej skróconej karcie są podane podstawowe informacje o wybranej transakcji magazynowej. Oprócz pól widocznych na **stronie Transakcje magazynowe**, zawiera ona również dodatkowe pola, które opisano dalej w tym artykule. |
| Aktualizacje | Ta skrócona karta zawiera informacje związane z fizycznym, finansowym i rozliczeniowym aspektami wybranej transakcji magazynowej. W zależności od bieżącego stanu transakcji niektóre pola mogą być puste. Jednak te pola są ustawiane automatycznie podczas zaksięgowania transakcji. Oprócz pól widocznych na **stronie Transakcje magazynowe**, ta skrócona karta zawiera dodatkowe pola opisane w dalszej części tego artykułu. |
| Księgowania w księdze | Na tej skróconej karcie pokazano typ księgowania i konto księgowe, które są używane do fizycznej aktualizacji, aktualizacji finansowej, fizycznego przychodu, opłat fizycznych, przychodów finansowych i opłat finansowych związanych z wybraną transakcją magazynowa. |
| Odwołania | Ta skrócona karta zawiera dodatkowe informacje o transakcji źródłowej, która utworzyła wybraną transakcję magazynowe. Te informacje mogą na przykład zawierać szczegóły z zamówienia zakupu lub sprzedaży. |
| Informacje pokrewne | Na tej skróconej karcie są podane dodatkowe informacje o wybranej transakcji magazynowej. Te pola mogą nie być ustawione, jeśli nie są one dostępne przez niektóre funkcje, takie jak kategorie zaopatrzenia lub projekty. |
| Wymiary finansowe – fizyczne | Na tej skróconej karcie są przedstawiane wartości wymiarów finansowych, które były używane podczas księgowania fizycznej aktualizacji. Jeśli fizyczna aktualizacja nie została zaksięgowana, pola będą puste. |
| Wymiary finansowe – finansowe | Na tej skróconej karcie są przedstawiane wartości wymiarów finansowych, które były używane podczas księgowania finansowej aktualizacji. Jeśli finansowa aktualizacja nie została zaksięgowana, pola będą puste. |
| Wymiary magazynowe | Ta skrócona karta zawiera wartości wymiarów magazynowych przypisanych do wybranej transakcji magazynowej. Wartości te obejmują lokalizację, magazyn, rozmiar, kolor, konfigurację, lokalizację, numer partii, numer seryjny, stan zapasów, numer rejestracyjny i właściciela. |

## <a name="fields-on-the-general-fasttab"></a>Pola na skróconej karcie Ogólne

W poniższej tabeli opisano pola na skróconej **karcie Ogólne**, które nie są także wyświetlane na **stronie Transakcje magazynowe**.

| Pole | Opis |
|---|---|
| Strona | Nazwa odpowiedniej strony dla wybranej transakcji magazynowej. Na przykład w transakcji zamówienia zakupu jest w nich przedstawiana nazwa dostawcy, a w transakcji zamówienia sprzedaży – nazwa odbiorcy. To pole nie jest dostępne dla wszystkich typów transakcji magazynowych. |
| Odwołanie do zapasów | Typ innej transakcji magazynowej, jeśli z wybraną transakcją magazynowej jest związana inna transakcja magazynowa. Na przykład, jeśli zamówienie zakupu jest oznaczone w zamówieniu sprzedaży, pole **Odwołanie do zapasów** transakcji zamówienia zakupu zostanie ustawione na *Zamówienie sprzedaży*. Zaznaczanie następuje automatycznie dla zamówień dostawy bezpośredniej i zamówień międzyfirmowych. W przypadku korzystania z zaznaczania metod wyceny innych niż *koszt standardowy* i *średnia ruchoma*, system utworzy rozliczenia i korekty dokładnych transakcji, które są zaznaczone. W ten sposób można uzyskać „rzeczywiste” koszty, które przesłaniają logikę dla pierwszego wejścia, pierwszego wyjścia (FIFO); ostatnie weszło, pierwsze wyszło (LIFO); lub średnia ważona. |
| Numer zamówienia magazynowego | Określonej transakcji związanej z wybraną transakcją magazynowymi. Na przykład, jeśli zamówienie zakupu jest oznaczone w zamówieniu sprzedaży, pole **Numer inwentarzowy** transakcji zamówienia zakupu zostanie ustawione na numer zamówienia sprzedaży. |
| Identyfikator projektu | Jeśli wybrana transakcja magazynowa jest związana z projektem, w tym polu jest ustawiany numer projektu. |
| Identyfikator partii | Unikatowy identyfikator partii przypisany przez system do wybranej transakcji magazynowej. |
| Partia odwołania | Jeśli inna transakcja magazynowa jest powiązana z wybraną transakcją magazynową, identyfikator partii tej innej transakcji. Na przykład, jeśli zamówienie zakupu jest oznaczone w zamówieniu sprzedaży, pole **Referencja partii** transakcji zamówienia zakupu będzie wartością **Identyfikator partii** wartości transakcji magazynowej w wierszu zamówienia sprzedaży. |
| Numer wymiaru | Unikatowy identyfikator reprezentujący kombinację wszystkich wartości wymiarów magazynowych przypisanych do wybranej transakcji magazynowej. |
| Wartość otwarta | Wartość wskazująca, czy wybrana transakcja magazynowa została rozliczona w procesie zamykania magazynu. Jeśli to pole jest ustawione na *Tak*, transakcja nie została rozliczona. |
| Oczekiwana data | W przypadku transakcji przychodu jest to oczekiwana data przyjęcia na magazyn. Na przykład w tym polu może być pokazywana oczekiwana data przyjęcia w zamówieniu blokowania zapasów lub data dostawy w wierszu zamówienia zakupu. |
| Data zapasów | To pole jest ustawiane, gdy transakcja rejestracji została wykonana na zamówieniu przychodu przed zaksięgowaniem fizycznego przychodu. |
| Przeniesienie niefinansowe | Wartość wskazująca, czy wybrana transakcja magazynowa jest przeniesieniem niefinansowym. Przeniesienie niefinansowe występuje, gdy zmiana wymiarów magazynowych nie jest śledzona pod finansami na stronie **grupy modeli towaru**. |
| Przeniesienie identyfikatora partii | Jeśli wybrana transakcja magazynowa jest przeniesieniem niefinansowym, w tym polu jest ustawiana wartość **identyfikatora partii** innej transakcji magazynowej, z która zostanie rozliczona wybrana transakcja. |

## <a name="fields-on-the-updates-fasttab"></a>Pola na skróconej karcie aktualizacji

W poniższej tabeli opisano pola na skróconej **karcie Aktualizacje**, które nie są także wyświetlane na **stronie Transakcje magazynowe**.

| Pole | Opis |
|---|---|
| Załącznik fizyczny | Numer załącznika z księgi głównej, w którym zostało wygenerowane fizyczne księgowanie wybranej transakcji magazynowej. |
| Trasa | Trasa powiązana z wybraną transakcją magazynową. To pole jest ustawiane tylko dla transakcji listy pobrania produkcji, w których wiersz BOM lub formuła jest powiązany z określonym towarem. |
| Dokument dostawy | Numer dokumentu dostawy wprowadzony dla transakcji dokumentu przyjęcia produktów zamówienia zakupu. |
| Fizyczna wartość kosztu | Kwota, która została zaksięgowana w księdze głównej w celu fizycznej aktualizacji. W przypadku produktu typu koszt standardowy ta kwota reprezentuje koszt standardowy. W przypadku innych metod wyceny reprezentuje on średnią ważoną produktu w momencie księgowania. |
| Fizyczne przychody | Kwota odroczonego przychodu, która została zaksięgowana w księdze głównej dla fizycznej aktualizacji. |
| Identyfikator ładunku | Jeśli bieżąca transakcja jest związana z ładunkiem w części Zarządzanie transportem, w tym polu jest uwzględniany unikatowy numer ładunku, który zawiera towar. |
| Zaksięgowane fizycznie | Wartość wskazująca, czy wybrana transakcja magazynowa została fizycznie zaksięgowana. Jeśli bieżąca transakcja zostanie zaksięgowana w księdze głównej, będzie także załącznik fizyczny. |
| Zaksięgowane finansowo | Wartość wskazująca, czy wybrana transakcja magazynowa została finansowo zaksięgowana. Jeśli bieżąca transakcja zostanie zaksięgowana w księdze głównej, będzie także załącznik finansowy. |
| Zaksięgowana opłata fizyczna | Wartość wskazująca, czy fizyczne opłaty związane z wybraną transakcją magazynową zostały zaksięgowane. |
| Zaksięgowane obciążenie finansowe | Wartość wskazująca, czy finansowe opłaty związane z wybraną transakcją magazynową zostały zaksięgowane. |
| Załącznik finansowy | Numer załącznika w księdze głównej, w której zostało wygenerowane księgowanie finansowe. |
| Faktura | Numer faktury wygenerowanej na przykład dla zamówienia zakupu lub sprzedaży. |
| Korekta | Kwota, która została skorygowana w wybranej transakcji magazynowej z procesu zamknięcia i korekty magazynu. |
| Wynikowe, kwota zaksięgowana | Kwota wybranej transakcji magazynowej zaksięgowana w zestawieniach zysków i strat. |
| Faktura niezaksięgowana | Numer faktury powiązanego zamówienia zakupu wyświetlany na stronie **Oczekująca faktura od dostawcy**. |
| Finansowo zamknięty | Data pełnego rozliczenia transakcji. |
| Pokryta ilość efektywna | Ilość w ilości catch, która jest pokryta przez rozliczenie. |
| Rozliczona ilość | Ilość rozliczona dla wybranej transakcji magazynowej. |
| Kwota rozliczona | Wartość, która została rozliczona dla wybranej transakcji magazynowej. |
