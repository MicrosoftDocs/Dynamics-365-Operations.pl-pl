---
title: Omówienie rozpoznawania przychodu (temat obejmuje film)
description: Ten artykuł zawiera informacje dotyczące funkcji Rozpoznawanie przychodu. Ta funkcja tworzy elastyczną strukturę, która umożliwia określanie reguł rozpoznawania zarówno ceny przychodu, jak i harmonogramu przychodu w przypadku zamówień wieloelementowych na poziomie danej firmy.
author: kweekley
ms.date: 03/15/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 1f1c42897a0392d053b90fc2eae9b20a0d14f327
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/29/2022
ms.locfileid: "9067721"
---
# <a name="revenue-recognition-overview"></a>Omówienie rozpoznawania przychodu

[!include [banner](../includes/banner.md)]

Firmy w branży sprzedające wiele elementów, jak produkty, usługi, subskrypcje itd., muszą być w stanie rozdzielać zamówienia wieloelementowe, aby przychód mógł zostać rozpoznany na podstawie zbioru wytycznych właściwych dla danej firmy i branży.

Funkcje rozpoznawania przychodów, w tym funkcja pakietu, nie są obsługiwane w kanałach Commerce (handel elektroniczny, punkt sprzedaży, biuro obsługi). Towary skonfigurowane pod kątem rozpoznawania przychodu nie powinny być dodawane do zamówień ani transakcji tworzonych w kanałach Commerce.

Proces rozpoznawania przychodu może generalnie służyć do wykonywania następujących zadań:

* Alokowanie przychodu, aby odpowiednia cena przychodu została rozpoznana na podstawie wartości składników w zamówieniach wieloskładnikowych.
* Odraczanie przychodu na podstawie harmonogramu przychodu, który reprezentuje uzgodniony w umowie przedział czasowy, i udziały procentowe rozpoznawania przychodu z biegiem czasu.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

Film [Sposób korzystania z rozpoznawania przychodów w Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) (widoczny powyżej) znajduje się na liście odtwarzania [aplikacji finansowych i operacyjnych](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) dostępnej w witrynie YouTube.

Funkcja Rozpoznawanie przychodu tworzy elastyczną strukturę, która umożliwia określanie reguł rozpoznawania zarówno ceny przychodu, jak i harmonogramu przychodu na poziomie danej firmy.

Zwolnione produkty służą do obsługi rozpoznawania przychodu w dokumentach zamówień sprzedaży. Zwolnione produkty zawierają ustawienia wymagane do określenia ceny przychodu i harmonogramu przychodów. Zamówienie sprzedaży może pochodzić z projektu typu czas i materiały.

Firmy mogą używać funkcji harmonogramu przychodów bez korzystania z funkcji ceny przychodu. W związku z tym cena w wierszach zamówienia sprzedaży zawsze zostanie użyta jako przychód lub odroczony przychód. Jeśli w wierszu zamówienia sprzedaży istnieje harmonogram przychodów, cena w wierszu zamówienia sprzedaży zostanie odroczona. Jeśli wiersz zamówienia sprzedaży nie zawiera harmonogramu przychodów, cena w wierszu zamówienia sprzedaży zostanie zaksięgowana na koncie przychodów po zafakturowaniu.

Cena przychodu jest obliczana w momencie zatwierdzenia zamówienia sprzedaży albo zaksięgowania faktury. Aby wyświetlić podgląd ceny przychodu przed zaksięgowaniem faktury, należy potwierdzić zamówienie sprzedaży.

Po potwierdzeniu zamówienia sprzedaży jest również tworzony oczekiwany harmonogram przychodów, jeśli dowolny wiersz zamówienia sprzedaży zawiera harmonogram przychodów. Po zafakturowaniu zamówienia sprzedaży oczekiwany harmonogram przychodów zostanie usunięty i zastąpiony rzeczywistym harmonogramem rozpoznawania przychodów.

Szczegóły harmonogramu rozpoznawania przychodu są obsługiwane dla każdego wiersza zamówienia sprzedaży. W związku z tym menedżer rozpoznawania przychodu może wyświetlać szczegóły i zwalniać wiersze do przychodu, gdy zobowiązanie umowne zostanie zrealizowane. Na koniec każdego okresu menedżer rozpoznawania przychodu może utworzyć arkusz przychodów w celu zwolnienia wierszy harmonogramu, które są należne w wyznaczonym przez niego dniu lub wcześniej. Ten arkusz przychodów nie jest natychmiast księgowany. W związku z tym menedżer rozpoznawania przychodu może sprawdzić, czy kwoty zwalniane z odroczonego do rzeczywistego przychodu są poprawne.

Jeśli zmiana umowna spowoduje dodanie nowego wiersza zamówienia sprzedaży do istniejącego zamówienia sprzedaży lub nowego zamówienia sprzedaży, można uruchomić proces zmiany alokacji w celu skorygowania ceny przychodu we wszystkich wierszach zamówień sprzedaży.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]

