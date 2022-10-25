---
title: Przegląd – Planowanie zapotrzebowania materiałowego sterowane popytem (Demand Driven Material Requirements Planning - DDMRP)
description: Ten artykuł zawiera informacje o Planowaniu zapotrzebowania materiałowego kierowanego popytem (DDMRP), metodologii planowania, która opiera się na rozdzieleniu podaży i popytu.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 31b45fdb92cf8a590ff77104f0c8015fb4d329d5
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689496"
---
# <a name="demand-driven-material-requirements-planning-ddmrp-overview"></a>Przegląd – Planowanie zapotrzebowania materiałowego sterowane popytem (Demand Driven Material Requirements Planning - DDMRP)

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

Od lat firmy stosują planowanie zapotrzebowania materiałowego (MRP) jako system obliczania materiałów i komponentów potrzebnych do wytworzenia produktu. Jednak obecnie łańcuchy dostaw uległy zmianie. Części mają dłuższy czas realizacji, ponieważ są coraz częściej sprowadzane z zagranicy. W związku z tym wiele firm zgłasza, że doświadcza braków lub nadwyżek magazynowych, ponieważ nie wie, ile zapasów powinno się zmagazynować. Jest też więcej wahań na rynku (czasem niedokładnie prognozowanych), a klienci żądają produktów o krótkim czasie realizacji. Dlatego na całym świecie występują niedobory w łańcuchu dostaw. Ponadto narzędzia MRP często dają planistom tysiące czynności do wykonania. Dlatego trudno jest wiedzieć, na czym się skupić. Często rozwiązaniem wielu z tych problemów jest przejście na Planowanie zapotrzebowania materiałowego kierowanego popytem (DDMRP).

DDMRP to metodologia planowania, która opiera się na rozdzieleniu podaży i popytu. To rozłączenie uzyskuje się przez ustawienie punktów rozłączenia. W przypadku tych pozycji utrzymywane są bufory, aby zapewnić odpowiednią ilość zapasów. Rozdzielenie podaży i popytu pomaga uniknąć "efektu bicza", ponieważ zmienność nie jest przenoszona przez łańcuch. (*Efekt bicza* odnosi się do tego, jak małe wahania popytu na poziomie detalicznym mogą powodować stopniowo większe wahania popytu na poziomie hurtowni, dystrybutora, producenta i dostawcy surowców). Każdy bufor ma za zadanie pokryć średnie zużycie części i może być dostosowany do nagłych wzrostów zapotrzebowania.

DDMRP okazał się wartościową metodologią planowania w zmiennych środowiskach, gdzie czas tolerancji klienta jest krótszy niż skumulowany czas realizacji.

## <a name="the-five-components-of-ddmrp"></a>Pięć składników DDMRP

DDMRP ma pięć kolejnych składników (kroków). Pierwsze trzy komponenty zasadniczo definiują początkową i ewolucyjną konfigurację modelu planowania zapotrzebowania materiałowego sterowanego zapotrzebowaniem. Dwa ostatnie elementy określają codzienne działanie metodologii.

1. **[Strategiczne pozycjonowanie zapasów](ddmrp-inventory-positioning.md)** - Zidentyfikuj punkty odłączenia w sieci łańcucha dostaw. Punkty odłączenia to określone punkty łańcucha dostaw, w których umieszczasz bufor zapasów, który będziesz monitorować i uzupełniać.
2. **[Profile i poziomy buforów](ddmrp-buffer-profile-and-levels.md)** - Dla każdego punktu rozłączenia określ rozmiary buforów (minimalna ilość, maksymalna ilość i punkt zamawiania) oraz ilość zamawianą.
3. **[Dynamiczna regulacja buforów](ddmrp-buffer-profile-and-levels.md#dynamic-adjustments)** - Dostosuj poziomy buforów na podstawie zmiennych parametrów operacyjnych lub planowanych przyszłych zdarzeń.
4. **[Planowanie sterowane popytem](ddmrp-planning.md)** — generuj zamówienia dostaw w razie potrzeby. Do tych zamówień dostawy należą zlecenia produkcyjne, zamówienia zakupu i zamówienia przeniesienia zapasów
5. **[Duża współpraca i widoczna realizacja](ddmrp-visual-and-collaborative-execution.md)** - Uruchom zamówienia na dostawy z pomocą wizualizacji.

DDMRP jest zwykle używany przez producentów, którzy mają wielopoziomowe zestawienia materiałów (BOM). Można ją jednak stosować również w sieciach dystrybucji i handlu detalicznego.

## <a name="ddmrp-in-dynamics-365-supply-chain-management"></a>DDMRP w Dynamics 365 Supply Chain Management

Kod DDMRP jest dołączony do firmy Microsoft Dynamics 365 Supply Chain Management i nie wymaga żadnych dodatkowych opłat licencyjnych. W Supply Chain Management funkcja DDMRP została dodana do istniejącego modułu **Planowania głównego**. Wymaga to jednak użycia dodatku Optymalizacja planowania. 

DDMRP jest zintegrowany z istniejącymi ustawieniami planowania w Supply Chain Management i jest używany razem z nimi, aby uzyskać odpowiednią konfigurację planowania dla Twojej firmy. Jest on kontrolowany przez nowy kod zasięgu, który jest zupełnie inny niż okres, min/max, wymaganie itd. Nie jest to nowy moduł i nie zastępuje istniejących funkcji planowania. Użytkownik ma jednak większą funkcjonalność.
