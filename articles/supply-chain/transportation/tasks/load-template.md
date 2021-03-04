---
title: Szablony ładunku
description: W tym temacie opisano sposób konfigurowania szablonów ładunków i kojarzenia szablonu ładunku z nowym ładunkiem.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLoadTemplate
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 1ea7f5244b483a1b9d6c55227c676a3878a71d83
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/25/2020
ms.locfileid: "4646424"
---
# <a name="load-templates"></a>Szablony ładunku

Podczas tworzenia nowego ładunku można przypisać szablon ładunku. Szablon ładunku zawiera informacje dotyczące sprzętu oraz miary, takie jak wysokość, szerokość, głębokość i objętość ładunku.

W tym temacie opisano sposób konfigurowania szablonów ładunków i kojarzenia szablonu ładunku z nowym ładunkiem.

## <a name="set-up-a-load-template"></a>Ustawianie szablonu ładunku

1. Wybierz kolejno **Zarządzanie transportem \> Ustawienia \> Kompilowanie ładunku \> Szablon ładunku**.
1. W okienku akcji wybierz opcję **Nowy**, aby dodać nowy szablon, lub wybierz **Edytuj**, aby edytować istniejący.
1. W wierszu nowego lub istniejącego szablonu należy określić następujące pola:

    - **Identyfikator szablonu ładunku** – wprowadź unikatowy identyfikator (ID) tworzonego szablonu ładunku.
    - **Sprzęt** – wybierz sprzęt, który należy użyć do wysłania ładunku.
    - **Wysokość ładunku**, **Szerokość ładunku** i **Głębokość ładunku** – wprowadź wymiary ładunku.
    - **Maks. dozwolona objętość ładunku** i **Maks. dozwolona waga ładunku** – wprowadź maksymalną dozwoloną objętość i wagę ładunku.
    - **Maksymalna dozwolona waga brutto** — wprowadź maksymalną dozwoloną wagę brutto ładunku. Masa brutto ładunku obejmuje zarówno tarę, jak i masę ładunku.
    - **Maksymalna dozwolona liczba części frachtu** – wprowadź maksymalną liczbę części frachtu, jaką może zawierać ładunek.
    - **Załadowana stertami podłoga ładunkowa** – wybierz to pole wyboru, aby użyć ładowania podłogowego. W scenariuszu ładowania podłogowego, pudła są ułożone od podłogi do sufitu i od ściany do ściany wewnątrz kontenera, aby zmaksymalizować wewnętrzną pojemność.

1. Na okienku akcji wybierz opcję **Zapisz**.

## <a name="associate-a-load-template-with-a-new-load"></a>Skojarz szablon ładunku z nowym ładunkiem

1. Wybierz kolejno opcje **Zarządzanie transportem \> Planowanie \> Warsztat planowania wysyłki ładunku**.
1. W górnej części strony wybierz jedną z następujących zakładek, w zależności od typu dokumentu źródłowego, dla którego tworzysz ładunek: **Wysyłki**, **Wiersze sprzedaży**, **Wiersze przeniesienia** lub **Wiersze zamówienia zakupu**. 
1. Wybierz konkretny dokument, dla którego chcesz zaplanować ładunek.
1. W okienku akcji na karcie **Popyt i podaż** w grupie **Dodaj** kliknij opcję **Do nowego transportu**.
1. W oknie dialogowym **Szablon ładunku** w polu **Identyfikator szablonu ładunku** wybierz szablon do zastosowania.
1. Wybierz przycisk **OK**, aby zastosować szablon.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]