---
title: Podział klientów na harmonogramy rozliczeń
description: W tym artykule opisano sposób dzielenia odbiorcy w przypadku korzystania z fakturowania subskrypcji.
author: JodiChristiansen
ms.date: 11/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-11-05
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: cfbe61ca4b7e809a8183f4622bf6db4fc83a4d83
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746319"
---
# <a name="customer-split-on-billing-schedules"></a>Podział klientów na harmonogramy rozliczeń

W harmonogramie fakturowania konto *płatnika* jest klientem, który otrzymuje fakturę zamówienia sprzedaży, aby móc zapłacić rachunek. W niektórych scenariuszach fakturę może zapłacić więcej niż jeden odbiorca. Funkcja **Podziału odbiorców** umożliwia dodawanie kolejnych odbiorców, których można rozliczyć za ten sam harmonogram fakturowania. Aby włączyć tę funkcję, przejdź do **Rozliczanie abonamentu \> Rozliczanie kontraktu cyklicznego \> Konfiguracja \> Parametry rozliczania kontraktu cyklicznego** i ustaw opcję **Podział klientów** na **Tak**.

## <a name="customer-split-on-the-billing-schedule-header"></a>Podział klientów w nagłówku harmonogramu rozliczeń

Po utworzeniu harmonogramu fakturowania do nagłówka harmonogramu fakturowania można dodać dodatkowych odbiorców.

Aby dodać klienta, wykonaj następujące kroki.

1. Na karcie **Harmonogram fakturowania** wybierz pozycję **Podział odbiorcy**. Pola **Konto odbiorcy** i **Nazwa konta odbiorcy** w górnej części określają konto odbiorcy przypisanego jako **odbiorca harmonogramu fakturowania**.

    > [!NOTE]
    > Konto odbiorcy, które dodasz, nie może być takie samo jak konto faktury.

2. Na karcie **Wiersze podziału odbiorcy** wybierz pozycję **Dodaj wiersz**.
3. Wybierz odbiorcy, a następnie wprowadź wartość procentową każdej faktury dla tego odbiorcy.
4. Domyślnie jako daty rozpoczęcia i zakończenia używane są daty rozpoczęcia i zakończenia harmonogramu fakturowania. Wprowadź inne daty rozpoczęcia i zakończenia, jeśli nowy odbiorca zapłaci określony procent tylko za część harmonogramu fakturowania. Na przykład jeśli harmonogram rozliczeń ma datę początkową 1 stycznia i datę końcową 31 grudnia, a nowy klient jest rozliczany w wysokości 40 procent przez pierwsze dziewięć miesięcy, jako datę początkową należy określić 1 stycznia, a jako datę końcową 30 września i wpisz **40,00** jako wartość procentową.

Do wierszy podziału klientów można dodać więcej niż jednego klienta. W tym przypadku całkowita wprowadzona wartość procentowa nie może przekroczyć 100 procent. Wprowadź numer referencyjny klienta i zapotrzebowanie klienta jako pola informacyjne, które będą wyświetlane w wierszu zamówienia sprzedaży podczas procesu **Generuj fakturę**.

W szczegółach wiersza zostaną podane informacje o kontakcie, adresie dostawy, adresie weksla i szczegółach płatności dodanych odbiorców. Ta informacja będzie wyświetlana również na zamówieniu sprzedaży dla odbiorców.

Po dodaniu informacji o podziale klientów do nagłówka harmonogramu fakturowania, jeśli w harmonogramie fakturowania znajdują się niezafakturowane wiersze harmonogramu fakturowania, zostanie wyświetlony następujący komunikat monitujący o wycofanie zmian: „Czy chcesz wycofać zmianę z nagłówek do linii? Zmiany spowodują aktualizację tylko wierszy harmonogramu rozliczeń, które nie są rozliczane”. Wybierz przycisk **Tak**, aby zaktualizować informacje o podziale odbiorcy w wierszu harmonogramu fakturowania. Zmiany nie zostaną zaktualizowane, jeśli linia harmonogramu rozliczeń została już rozliczona.

Jeśli harmonogram fakturowania został utworzony za pomocą opcji **Kopiuj harmonogram**, informacje domyślne będą wprowadzane w wierszach nagłówka podziału odbiorcy. Nie może być taki sam jak konto odbiorcy.

Po zakończeniu procesu **generowania faktury** zostanie utworzonych wiele zamówień sprzedaży. (Wielokrotne faktury sprzedaży zostaną również utworzone, jeśli używane jest automatyczne księgowanie.) Te zamówienia sprzedaży i faktury sprzedaży można przeglądać na karcie **Faktura** w **Szczegóły wiersza** Skrócona karta strony **Wyświetl szczegóły fakturowania**. **Wiele** jest wyświetlane w wierszu szczegółów fakturowania, aby wskazać, że utworzono wiele zamówień sprzedaży i faktur sprzedaży.

## <a name="customer-split-on-billing-schedule-lines"></a>Podział klientów według linii harmonogramu rozliczeń

Podział klientów można dodać do poszczególnych wierszy harmonogramu rozliczeń, jeśli chcesz podzielić tylko określone wiersze harmonogramu rozliczeń. Zaznacz pole wyboru **Podział klientów** w wierszu, a następnie wybierz opcję **Podział klientów** w menu wiersza harmonogramu rozliczeń do aktualizacji lub wprowadź informacje o podziale klientów.

Informacje audytu są aktualizowane, jeśli harmonogram fakturowania został już zafakturowany, ale następnie zmieniono wartość procentową w wierszu harmonogramu fakturowania. Wszystkie wiersze rozliczane po tej zmianie będą używać nowej wartości procentowej.

> [!NOTE]
> - Nie można użyć opcji podziału odbiorcy z produktami magazynowanych.
> - Jeśli pole wyboru **Nierozliczone przychody** jest zaznaczone, nie można zaznaczyć pola wyboru **Podział klientów**.
> - Jeśli używasz opcji **Tylko podział przychodu**, wiersz nadrzędny ma opcję **Podział odbiorcy**, ale podrzędne elementy wiersza nie.
