---
title: Wystawiaj faktury elektroniczne w Finance i Supply Chain Management
description: W tym temacie wyjaśniono, jak wystawiać faktury elektroniczne w Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management za pomocą fakturowania elektronicznego.
author: gionoder
ms.date: 03/29/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 24909c2a2505724c159e939535c1d57cb66e48629862bebb32b3d72c0eb06c97
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752133"
---
# <a name="issue-electronic-invoices-in-finance-and-supply-chain-management"></a>Wystawianie faktur elektronicznych w rozwiązaniach Finance i Supply Chain Management

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak wystawiać faktury elektroniczne w Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management za pomocą fakturowania elektronicznego.


## <a name="feature-activation"></a>Aktywacja funkcji

Aby rozpocząć wystawianie faktur elektronicznych za pośrednictwem Fakturowania elektronicznego, należy aktywować odniesienie do funkcji w rozwiązaniu Finance i Supply Chain Management.

Każde odniesienie do funkcji odpowiada określonej funkcji fakturowania elektronicznego, która jest zgodna z wymaganiami dotyczącymi fakturowania elektronicznego w kraju / regionie.

W poniższej tabeli przedstawiono listę funkcji obsługiwanych przez Fakturowanie elektroniczne.

| Imię i nazwisko                                              | Kraj/region |
|---------------------------------------------------|----------------|
|Austriacka faktura elektroniczna                        |Austria         |
|Belgijska faktura elektroniczna                         |Belgia         |
|NF-e Federal — Brazylijska faktura elektroniczna       |Brazylia          |
|NFS-e — faktura elektroniczna usługi brazylijskiej (miasto)|Brazylia          |
|Duńska faktura elektroniczna                          |Dania         |
|Egipska faktura elektroniczna                        |Egipt           |
|Estońska faktura elektroniczna                        |Estonia         |
|Fińska faktura elektroniczna                         |Finlandia         |
|Francuska faktura elektroniczna                          |Francja          |
|Niemiecka faktura elektroniczna                          |Niemcy         |
|PEPPOL — globalna faktura elektroniczna                 |Globalna          |
|Włoska faktura elektroniczna                         |Włochy           |
|CFDI — Meksykańska faktura elektroniczna                  |Meksyk          |
|Holenderska faktura elektroniczna                           |Holandia     |
|Norweska faktura elektroniczna                       |Norwegia          |
|Hiszpańska faktura elektroniczna                         |Hiszpania           |

Jeśli istnieje starsza funkcja fakturowania elektronicznego, która jest obsługiwana w zakresie lokalizacji kraju / regionu, aktywacja jednej z tych funkcji wyłącza starszą funkcję i umożliwia wystawianie faktur elektronicznych za pośrednictwem Fakturowania elektronicznego.

> [!IMPORTANT]
> Po włączeniu funkcji integracji Fakturowania elektronicznego nowe doświadczenie w fakturowaniu elektronicznym jest domyślnie wyłączone. Za pomocą koncepcji funkcji można selektywnie włączyć nowe możliwości dla firm za pomocą funkcji specyficznych dla kraju/regionu. Opcja **Global** określa nowe możliwości dla pozostałych powiatów/regionów, które nie zostały wyszczególnione w tabeli.

## <a name="submit-electronic-documents"></a>Prześlij dokumenty elektroniczne

Proces przesyłania dokumentów elektronicznych stanowi pojedynczy punkt komunikacji między działem Finance i Supply Chain Management a fakturowaniem elektronicznym. Podczas każdego zdarzenia przesyłania komunikacja przebiega w obu kierunkach:

- **Od Finance i Supply Chain Management po fakturowanie elektroniczne** — Finance i Supply Chain Management wysyła abstrakcyjne faktury do Fakturowania elektronicznego. W razie potrzeby wysyłają również zawartość zmiennych, które zostały skonfigurowane w ramach funkcji fakturowania elektronicznego.
- **Od fakturowania elektronicznego po Finance i Supply Chain Management** — W zależności od funkcji fakturowania elektronicznego oprogramowanie Finance i Supply Chain Management otrzymuje aktualizacje z dodatku Fakturowanie elektroniczne dotyczące wyników przetwarzania faktur, które zostały wcześniej przesłane. Otrzymują również zawartość zmiennych, które zostały skonfigurowane w ramach funkcji fakturowania elektronicznego.

Aby przesłać dokumenty elektroniczne do Fakturowania elektronicznego, w obszarze Finance i Supply Chain Management przejdź do **Administrowanie organizacją &gt; Okresowe &gt; Dokumenty elektroniczne &gt; Prześlij dokumenty elektroniczne**.

Punktem początkowym jest zaksięgowana faktura. Faktura może pochodzić z różnych źródeł, takich jak zamówienia sprzedaży, faktury projektów lub faktury tekstowe.

Proces przesyłania można uruchomić ręcznie lub w tle.

- **Wykonanie ręczne** — w przypadku wykonywania ręcznego należy użyć opcji **Filtruj**, aby zdefiniować zakres dokumentów, które muszą zostać przesłane. Na stronie **Filtry** można skonfigurować własną kwerendę wybierającą zaksięgowane faktury, które muszą zostać przesłane. Po dokonaniu wyboru należy ręcznie rozpocząć przetwarzanie i poczekać na jego zakończenie. Po zakończeniu przetwarzania komunikat w Centrum akcji pokazuje liczbę dokumentów elektronicznych, które zostały pomyślnie przesłane.
- **Wykonywanie w tle** – Wykonywanie w tle działa bez wymogu logowania lub zachowania otwartego okna dialogowego przesyłania. Możesz zaplanować uruchomienie procesu i określić częstotliwość wykonywania.

## <a name="view-the-submission-logs"></a>Wyświetlanie dzienników przesyłania

W Finance i Supply Chain Management można używać dzienników przesyłania, aby wyświetlić wyniki przetwarzania przesyłania do fakturowania elektronicznego. Przejdź do formularza **Administrowanie organizacją &gt; Okresowe &gt; Dokumenty elektroniczne &gt; Przesyłanie dokumentów elektronicznych**, a następnie w polu **Typ dokumentu** wybierz wartość, aby filtrować typ faktur, jakie są wyświetlane w dziennikach.

Istnieją trzy możliwe stany przesyłania:

- **Zaplanowano** — Dodatek do elektronicznego fakturowania otrzymał przesłanie z Finance i Supply Chain Management, a przetwarzanie funkcji fakturowania elektronicznego jest w toku.
- **Ukończono** — fakturowanie elektroniczne zostało pomyślnie przetworzone przez funkcję fakturowania elektronicznego skonfigurowaną do uruchomienia.
- **Błąd** — fakturowanie elektroniczne napotkało błąd lub zostało zatrzymane przez wyjątek podczas przetwarzania funkcji fakturowania elektronicznego.

> [!IMPORTANT]
> Stan przesyłania dotyczy stanu przetwarzania, które zawiera Fakturowanie elektroniczne w funkcji fakturowania elektronicznego. Nie dotyczy on ostatecznego stanu samej faktury elektronicznej.
>
> Na przykład, jeśli faktura elektroniczna musi zostać przesłana do zatwierdzenia do zewnętrznej usługi sieci web, stan przesyłania może mieć stan **Zakończono**, ale stan faktury elektronicznej może być **Odrzucony**. W tym przypadku Fakturowanie elektroniczne było w stanie pomyślnie przetworzyć funkcję fakturowania elektronicznego, ponieważ jest skonfigurowana do przetwarzania tej funkcji. Jednak faktura elektroniczna została odrzucona, ponieważ nie spełniała kryteriów ustalonych przez usługę sieciową w celu zatwierdzenia faktury.

Dzienniki przesyłania zawierają następujące funkcje dodatkowe:

- **Szczegóły przesłania** – Wyświetl szczegóły głównego przesyłania. Wizualizacja pokazuje pełny dziennik wykonywania akcji skonfigurowanych w funkcji fakturowania elektronicznego. Pozwala także użytkownikom na pobieranie plików tworzona podczas przetwarzania. W scenariuszach, w których faktura musi zostać zatwierdzona przez zewnętrzną usługę sieciową, umożliwia użytkownikom przeglądanie statusu faktury.
- **Powiązane przesłania** – Wyświetl szczegóły przesłania podrzędnego.
- **Anulowanie przesyłania** — ta funkcja umożliwia specjalny proces przesyłania w scenariuszach, w których faktura elektroniczna musi zostać zatwierdzona przez zewnętrzną usługę sieci web. Nakazuje Fakturowaniu elektronicznemu wysłanie do usługi sieciowej określonej wiadomości, która ma na celu anulowanie statusu zatwierdzonej faktury elektronicznej w bazie danych usługi internetowej.
- **Ponowne prześlij dokument** — prześlij ponownie dokument elektroniczny, który został już przesłany do Fakturowania elektronicznego. Na stronie **Szczegóły przesyłania** jest tworzony nowy dziennik.
- **Wysyłanie powiązanego przesłania**


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
