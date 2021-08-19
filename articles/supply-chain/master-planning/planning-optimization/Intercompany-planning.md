---
title: Planowanie międzyfirmowe
description: W tym temacie opisano planowanie międzyfirmowe i wyjaśniono sposób konfigurowania planowania międzyfirmowego przy użyciu optymalizacji planowania w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 2bf69a5d0d6e070374277e2d82d5fbf6eb4b8704895ffe31aa7e2d2d3546bb16
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6777918"
---
# <a name="intercompany-planning"></a>Planowanie międzyfirmowe

[!include [banner](../../includes/banner.md)]

W niektórych organizacjach operacje logistyczne zależą od innych osób prawnych (firm) w organizacji. Operacje te są obsługiwane przy użyciu międzyfirmowych procesów sprzedaży i zakupów, ponieważ każda osoba prawna ma osobny plan kont.

W tym temacie opisano planowanie międzyfirmowe i wyjaśniono sposób konfigurowania planowania międzyfirmowego przy użyciu optymalizacji planowania w rozwiązaniu Microsoft Dynamics 365 Supply Chain Management.

W tym temacie są używane następujące ważne terminy związane z obrotem międzyfirmowym:

- **Od odbiorcy do dostawcy** — odwołanie względne w łańcuchu firm lub dostaw. Oznacza przesunięcie w kierunku dostawcy surowca.
- **Od dostawcy do odbiorcy** — odwołanie względne w łańcuchu firm lub dostaw. Oznacza przesunięcie w kierunku odbiorcy.
- **Zaplanowany popyt międzyfirmowy** — planowane zapotrzebowanie na produkt w firmie, w oparciu o planowane zapotrzebowanie na produkt w firmie podrzędnej.

W planowaniu głównym plan jednej firmy może zawierać zaplanowany popyt międzyfirmowy związany z zamówieniami planowanymi w planie innej firmy. Jest to przydatna możliwość, ponieważ daje pełen wgląd w planowane zamówienia między firmami. Ponadto zapewnia, że wszystkie wymagane planowane zamówienia podażowe są tworzone, ale bez konieczności akceptowania zamówień planowanych dla popytu międzyfirmowego.

W przypadku uruchomienia planowania głównego z planu głównego, który zawiera planowany popyt od dostawcy do odbiorcy, planowane zamówienia zakupu od powiązanych dostawców międzyfirmowych będą uwzględniane w planie jako zapotrzebowanie.

## <a name="required-setup"></a>Wymagana konfiguracja

Aby skorzystać z planowania międzyfirmowego, należy przygotować system w następujący sposób:

1. Odpowiednie produkty muszą być zwolnione we wszystkich odpowiednich firmach. Aby uzyskać więcej informacji, zobacz [Konfigurowanie i używanie handlu międzyfirmowego w Dynamics 365 Supply Chain Management](/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) w Microsoft Learn.
1. Popyt od dostawcy do odbiorcy musi być pokryty zakupami od dostawcy, który pozostaje w relacji międzyfirmowej z firmą nadrzędną oraz odpowiednimi wymiarami magazynowymi (oddział i magazyn) odbiorcy. Aby uzyskać więcej informacji, zobacz [Konfigurowanie i używanie handlu międzyfirmowego w Dynamics 365 Supply Chain Management](/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) w Microsoft Learn.
1. Plan główny w firmie obsługującej przełączenie musi zawierać planowane zapotrzebowanie na zamówienie podrzędne, a odpowiednia firma i plan główny muszą być określone w planach podrzędnych.

## <a name="include-planned-downstream-demand"></a>Uwzględnij planowany popyt od dostawcy do odbiorcy

Wykonaj poniższe kroki, aby skonfigurować swój plan główny, tak aby uwzględniał planowany popyt od dostawcy do odbiorcy.

1. Przejdź do **Planowanie główne \> Ustawienia \> Plany \> Plany główne**.
1. Wybierz lub utwórz plan główny.
1. Na skróconej karcie **planowania międzyfirmowego** ustaw następujące pola:

    - **Uwzględnij planowany popyt od dostawcy do odbiorcy** — ustawienie tej opcji na wartość *Tak* spowoduje włączenie planowania międzyfirmowego dla planu głównego.
    - **Plany od dostawcy do odbiorcy** — w przypadku ustawienia opcji **Uwzględnij planowany popyt od dostawcy do odbiorcy** na wartość *Tak* należy użyć paska narzędzi i siatki, aby dodać żądane plany główne z innych firm.

## <a name="peg-across-companies-by-using-multilevel-pegging"></a>Ustalanie między firmami przy użyciu wielopoziomowego oznaczania transakcji

W przypadku wielopoziomowego oznaczania transakcji można wyświetlić oznaczanie transakcji między firmami, aby zobaczyć początkowe źródło popytu, które jest objęte dostawą.

Aby wyświetlić informacje o wielopoziomowym oznaczaniu transakcji, wykonaj następujące kroki.

1. Wybierz kolejno opcje **Planowanie główne \> Planowanie główne \> Zamówienia planowane**.
1. Wybierz lub otwórz zamówienie planowane.
1. W okienku akcji, na karcie **Widok** w grupie **Wymagania** wybierz **Wielopoziomowe oznaczanie transakcji**.

### <a name="intercompany-example-that-involves-two-companies"></a>Przykład obrotu międzyfirmowego obejmujący dwie firmy

W tym przykładzie planowane zlecenie produkcyjne jest tworzone w firmie USMF w celu pokrycia zamówienia sprzedaży firmy DEMF. W firmie USMF bezpośrednie zapotrzebowanie jest zaplanowanym popytem międzyfirmowym. Aby to zapotrzebowanie pojawiło się w firmie USMF, planowanie główne jest uruchamiane najpierw w firmie DEMF, a następnie w firmie USMF.

Na poniższej ilustracji pokazano, jak ten przykład może wyglądać na stronie **Wielopoziomowe oznaczanie transakcji** dla planowanego zlecenia produkcyjnego.

![Przykład obrotu międzyfirmowego obejmujący dwie firmy.](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a>Przykład obrotu międzyfirmowego obejmujący trzy firmy

W tym przykładzie planowane zamówienie zakupu jest tworzone w firmie USMF w celu pokrycia zamówienia sprzedaży firmy FRRT. W firmach DEMF and USMF bezpośrednie zapotrzebowanie jest zaplanowanym popytem międzyfirmowym. Aby to zapotrzebowanie pojawiło się w firmie USMF, planowanie główne jest uruchamiane najpierw w firmie FRRT, następnie w firmie DEMF, a na końcu w firmie USMF.

Na poniższej ilustracji pokazano, jak ten przykład może wyglądać na stronie **Wielopoziomowe oznaczanie transakcji** dla planowanego zlecenia produkcyjnego.

![Przykład obrotu międzyfirmowego obejmujący trzy firmy.](media/IntercompanyPlanning2.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]