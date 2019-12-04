---
title: Rozpoznawanie przychodów z zamówień sprzedaży
description: W tym temacie opisano podstawową funkcję rozpoznawania przychodów z zamówień sprzedaży i faktur. Rozpoznawanie przychodów jest dostępne w zamówieniu sprzedaży i na odpowiedniej fakturze utworzonej z zamówienia sprzedaży.
author: kweekley
manager: aolson
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 6e2eafc6785aaf9bc7421bc80c90fa4a7f98a2d4
ms.sourcegitcommit: 92322167f57b66d2accc134aaf862e6b9931ec94
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/31/2019
ms.locfileid: "2693027"
---
# <a name="revenue-recognition-on-sales-orders"></a>Rozpoznawanie przychodów z zamówień sprzedaży

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Funkcji Rozpoznawanie przychodów nie można włączyć za pomocą modułu Zarządzanie funkcjami. Obecnie można ją włączyć tylko przy użyciu kluczy konfiguracji.

W tym temacie opisano podstawową funkcję rozpoznawania przychodów z zamówień sprzedaży i faktur. Rozpoznawanie przychodów jest dostępne w zamówieniu sprzedaży i na odpowiedniej fakturze utworzonej z zamówienia sprzedaży. Zamówienie sprzedaży można również utworzyć za pomocą projektu typu czas i materiały.

> [!NOTE]
> Na ilustracjach w tym temacie kolumny zostały ukryte lub dodane do siatek, aby lepiej pokazać koncepcje. Z tego względu strony i dane na ilustracjach mogą się różnić od tego, co widać w produkcie.

## <a name="enter-a-sales-order"></a>Wprowadzanie zamówienia sprzedaży

Wprowadzono następujące zamówienie sprzedaży i obejmuje ono trzy elementy skonfigurowane dla rozpoznawania przychodów.

[![Wprowadzanie zamówienia sprzedaży](./media/revenue-recognition-so-basic-sales-order-header.png)](./media/revenue-recognition-so-basic-sales-order-header.png)

Istnieją dwie koncepcje rozpoznawania przychodów:

- **Określanie ceny przychodu.** Cena przychodu jest obliczana na podstawie konfiguracji zwolnionych produktów. Cena przychodu nigdy nie jest pokazywana odbiorcy, służy tylko do księgowania faktury zamówienia sprzedaży. Wiersze zamówienia sprzedaży i dokumenty drukowane w ramach sprzedaży nadal pokazują cenę jednostkową/katalogową.
- **Określanie, kiedy powinno nastąpić rozpoznanie przychodów.** Do ustalenia, kiedy powinno nastąpić rozpoznanie przychodów, służy harmonogram przychodów.

    W tym przykładzie pierwsza pozycja S0001 jest przypisana do harmonogramu przychodów **1O** (jedno wystąpienie). Ten wiersz przedstawia scenariusz typu kamień milowy, w którym przychód zostanie rozpoznany po instalacji w przyszłości. Z tego względu przychód zostanie odroczony do momentu zakończenia instalacji.

    Druga pozycja S0008 to usługa skonfigurowana jako element obsługi po wygaśnięciu umowy (PCS). Długotrwałe usługi inżynieryjne są świadczone na rzecz odbiorcy przez okres 12 miesięcy. W związku z tym do produktu domyślnie przypisany jest harmonogram przychodów **12M**. Ponieważ ta pozycja jest elementem PCS, należy określić daty rozpoczęcia i zakończenia umowy. Domyślnie daty rozpoczęcia i zakończenia umowy znajdują się w sekcji Szczegóły pozycji w zakładce Ustawienia. W harmonogramie przychodów konfiguracja **12M** jest zdefiniowana tak, że warunki umowy są automatycznie wypełniane, jak pokazano na poniższej ilustracji.

    [![Harmonogramy przychodów](./media/revenue-recognition-so-basic-revenue-schedules.png)](./media/revenue-recognition-so-basic-revenue-schedules.png)

    Trzecia pozycja S0012 to sprzęt i domyślnie nie jest przypisany żaden harmonogram przychodów. Przychody ze sprzętu są uznawane, gdy tylko produkt zostanie zafakturowany.

## <a name="confirm-the-sales-order"></a>Potwierdzanie zamówienia sprzedaży

Aby wyświetlić dodatkowe szczegóły dotyczące ceny i harmonogramu przychodów, użyj przycisków w grupie **Rozpoznawanie przychodów** na karcie **Zarządzaj** w okienku akcji zamówienia sprzedaży. Ponieważ w tym momencie zamówienie sprzedaży nie jest potwierdzone, przyciski używane do rozpoznawania przychodów są niedostępne. Przyciski te stają się dostępne lub niedostępne, gdy zamówienie sprzedaży przechodzi przez etapy prowadzące do jego realizacji.

[![Nagłówek zamówienia sprzedaży](./media/revenue-recognition-so-basic-sales-order-header-02.png)](./media/revenue-recognition-so-basic-sales-order-header-02.png)

Pierwsze trzy przyciski zawierają szczegółowe informacje o cenie przychodu dla pozycji w konfiguracji zamówienia sprzedaży w celu rozpoznania przychodów.

- **Alokacja ceny przychodu** — ten przycisk staje się dostępny po potwierdzeniu zamówienia sprzedaży lub zaksięgowaniu faktury. Zarówno potwierdzenie zamówienia sprzedaży, jak i księgowanie faktury obliczają przychód w celu rozpoznania ceny, która zostanie uznana lub odroczona na wpisie księgowania. W zależności od konfiguracji obliczana cena przychodu może różnić się od ceny jednostkowej pokazywanej odbiorcy.
- **Zmień alokację ceny za pomocą nowych wierszy zamówienia** — ten przycisk staje się dostępny po potwierdzeniu zamówienia sprzedaży lub zaksięgowaniu faktury. Proces zmiany alokacji służy do ponownego obliczenia przychodu, który musi zostać rozpoznany po dodaniu nowego wiersza do bieżącego zamówienia sprzedaży lub do nowego zamówienia sprzedaży albo po zafakturowaniu. W obu scenariuszach dodanie nowego elementu powoduje zmianę umowy. Z tego względu należy zmienić alokację ceny przychodu.
- **Zaktualizuj alokację ceny przychodu** — ten przycisk staje się dostępny po potwierdzeniu zamówienia sprzedaży, ale staje się niedostępny po zafakturowaniu zamówienia sprzedaży. Aktualizacja służy do ponownego uruchomienia alokacji ceny przychodu bez konieczności potwierdzania zamówienia sprzedaży. Po zafakturowaniu zamówienia sprzedaży nie można ponownie obliczyć ceny przychodu.

Dwa ostatnie przyciski zawierają szczegółowe informacje o harmonogramie przychodów dla pozycji w zamówieniu sprzedaży z harmonogramem przychodów.

- **Oczekiwany harmonogram rozpoznawania przychodów** — ten przycisk staje się dostępny po potwierdzeniu zamówienia sprzedaży, ale staje się niedostępny po zafakturowaniu zamówienia sprzedaży. Otwiera stronę z oczekiwanym harmonogramem przychodów. Ostateczny harmonogram może ulec zmianie, ponieważ oczekiwany harmonogram korzysta z żądanej daty wysyłki, podczas gdy ostateczny harmonogram używa rzeczywistej daty wysyłki.
- **Harmonogram rozpoznawania przychodów** — ten przycisk staje się dostępny po zafakturowaniu zamówienia sprzedaży. Ostateczny harmonogram rozpoznawania przychodów nie jest tworzony w przypadku potwierdzenia lub utworzenia dokumentu dostawy. Jest tworzony tylko wtedy, gdy zamówienie sprzedaży jest fakturowane.

W poniższym przykładzie alokacja ceny przychodu nastąpiła po potwierdzeniu zamówienia sprzedaży. Należy zauważyć, że mimo iż ceny przychodów są alokowane w różny sposób, łączna kwota w polu **Przychód do rozpoznania** musi być równa sumie wierszy zamówienia sprzedaży, które są zafakturowane do odbiorcy. Na przykład suma wierszy zamówienia sprzedaży wynosi 1499 USD (bez podatku). Dlatego suma wartości **Przychód do rozpoznania** musi również wynosić 1499 USD.

[![Alokacja ceny przychodu](./media/revenue-recognition-so-basic-revenue-price-allocation.png)](./media/revenue-recognition-so-basic-revenue-price-allocation.png)

Tworzony jest również oczekiwany harmonogram rozpoznawania przychodów. Harmonogram przychodów wykorzystuje **Przychód do rozpoznania** jako kwotę do odroczenia. Pozycja S0001 odracza 321,21 USD zamiast 300 USD, a pozycja S0008 odracza 160,61 USD zamiast 100 USD. Pozycja S0012 nie jest wyświetlana w oczekiwanym harmonogramie, ponieważ przychód nie jest odroczony. W momencie księgowania pozycja S0012 księguje 1017,18 USD bezpośrednio na koncie księgowym odroczonego przychodu.

[![Oczekiwany harmonogram rozpoznawania przychodów.](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)

## <a name="create-the-packing-slip"></a>Tworzenie dokumentu dostawy

Następnie można utworzyć dokument dostawy dla zamówienia sprzedaży. Po zaksięgowaniu dokumentu dostawy przychody nie są uznawane. Jeśli zamówienie sprzedaży nie zostanie potwierdzone, księgowanie dokumentu dostawy nie spowoduje obliczenia ceny przychodu. Nie uruchomi również tworzenia oczekiwanego lub końcowego harmonogramu rozpoznawania przychodów. Jeśli grupa modeli pozycji została skonfigurowana w celu odroczenia przychodów na dokumencie dostawy, będzie kontynuować księgowanie przy użyciu bieżących kont księgowych, a nie nowych kont odroczonych przychodów, które są używane w księgowaniu faktury.

## <a name="create-the-invoice"></a>Tworzenie faktury

Ostatnim krokiem jest wystawienie faktury za zamówienie sprzedaży. Jeśli spojrzysz na załącznik faktury, zauważysz, że przychód z pozycji S0001 i S0008 został odroczony (321,21 USD + 160,61 = 481,82), a pozostała kwota z pozycji S0012 została zaksięgowana w przychodzie (1017,18). Wartości te sumują się do 1499 USD, co odpowiada sumie wierszy zamówienia sprzedaży.

[![Transakcje z załącznikami](./media/revenue-recognition-so-voucher-transactions.png)](./media/revenue-recognition-so-voucher-transactions.png)

Po utworzeniu faktury, przyciski **Alokacja ceny przychodów**, **Zmień alokację ceny za pomocą nowych wierszy zamówienia** i **Harmonogram rozpoznawania przychodów** stają się dostępne, ale przyciski **Zaktualizuj alokację ceny przychodu** i **Oczekiwany harmonogram rozpoznawania przychodów** są niedostępne.

[![Dostępność przycisku rozpoznawania przychodów](./media/revenue-recognition-so-basic-after-invoice-buttons.png)](./media/revenue-recognition-so-basic-after-invoice-buttons.png)

Przycisk **Alokacja ceny przychodu** jest nadal dostępny, dzięki czemu można wyświetlić kalkulację ceny przychodu. Jeśli nic nie zmieniło się w zamówieniu sprzedaży po jego potwierdzeniu, kwota w polu **Przychód do rozpoznania** nie zostanie zmieniona podczas księgowania faktury.

Harmonogram oczekiwanego rozpoznawania przychodów zostanie usunięty i zastąpiony ostatecznym harmonogramem rozpoznawania przychodów. Szczegóły harmonogramu przychodu są zachowywane dla każdego wiersza zamówienia sprzedaży i są wykorzystywane do zwalniania przychodów odroczonych do faktycznych przychodów, gdy zobowiązania umowne zostaną spełnione.

[![Ostateczny harmonogram rozpoznawania przychodów.](./media/revenue-recognition-so-revenue-recognition-schedule.png)](./media/revenue-recognition-so-revenue-recognition-schedule.png)
