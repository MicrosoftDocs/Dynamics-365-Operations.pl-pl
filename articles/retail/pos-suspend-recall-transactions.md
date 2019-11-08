---
title: Wstrzymywanie i wznawianie transakcji w punkcie sprzedaży (POS)
description: W tym temacie opisano, jak użytkownicy mogą zawiesić transakcje w trakcie wykonywania i następnie wznowić je później lub na innej kasie przy użyciu Dynamics 365 Retail.
author: jblucher
manager: AnnBe
ms.date: 11/27/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 261234
ms.assetid: 7cd68ecc-cc09-48ab-8cb8-48d5c304effa
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 38011f094c1434e3cafe62629902b1556df73566
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/03/2019
ms.locfileid: "2552425"
---
# <a name="suspend-and-resume-a-transaction-in-the-point-of-sale-pos"></a>Wstrzymywanie i wznawianie transakcji w punkcie sprzedaży (POS)

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

Użytkownicy w punkcie sprzedaży (POS) mogą zawieszać transakcje w trakcie wykonywania, a następnie wznawiać je później lub na innej kasie. Transakcje są często wstrzymane w celu szybkiego zwolnienia kasy do innego zadania bez utraty postępu w bieżącej transakcji. Na przykład pracownik sklepu rozpoczyna przetwarzanie transakcji klienta na urządzeniu przenośnym, ale musi ją zakończyć na urządzeniu z szufladą kasową. W takim przypadku pracownik sklepu może zawiesić transakcję na urządzeniu przenośnym i następnie przywołać ją i wznowić na kasie.

## <a name="configure-suspend-and-resume-functionality"></a>Konfigurowanie funkcji wstrzymywania i wznawiania

### <a name="pos-operations"></a>Operacje aplikacji POS

Dwie [operacje POS](pos-operations.md) obsługują w POS scenariusze wstrzymywania i wznawiania. Można przypisać te operacje do [siatki przycisków](pos-screen-layouts.md) na stronie transakcji lub powitalnej.

- 503: Zawieś transakcję
- 504: Wznów transakcję

### <a name="receipt-template"></a>Szablon paragonu

Punktu sprzedaży można skonfigurować do generowania drukowanego dokumentu, gdy transakcja została zawieszona. Następnie można szybko użyć tego dokumentu do zidentyfikowania i przywołania transakcji później.

Aby umożliwić drukowanie dokumentu w punkcie sprzedaży, należy dodać format paragonu **Zawieszona transakcja** do profilu paragonów w sklepie. Można zaprojektować format paragonu, aby zawierał lub ignorował konkretne informacje na temat transakcji. Na przykład format może zawierać kod kreskowy obsługujący skanowanie.

### <a name="receipt-numbering"></a>Numeracja paragonów

Tak jak w przypadku innych typów transakcji w punkcie sprzedaży, które generują drukowane pokwitowanie, można zdefiniować sekwencję dla zawieszonych transakcji w sekcji **Numerowanie paragonów** sekcji profilu funkcji sklepu.

### <a name="void-when-closing-shift"></a>Unieważnij podczas zamykania zmiany

Można użyć opcji **Unieważnij podczas zamykania zmiany**, aby wymagać od użytkowników ukończenia lub unieważnienia podejrzanych transakcji przed zamknięciem zmiany. Podczas operacji **Zamknij zmianę** punkt sprzedaży będzie monitował użytkowników o wyświetlanie lub unieważnienie wszelkich zaległych zawieszonych transakcji.

## <a name="suspend-and-resume-a-transaction"></a>Zawieszanie i wznawianie transakcji

### <a name="suspend-a-transaction"></a>Zawieszanie transakcji

Użytkownicy, którzy mają wystarczające uprawnienia i mają układ ekranu zawierający operację **Zawieś transakcję**, mogą zawiesić transakcję, dzięki czemu można ją wywołać później lub na innej kasie.

Transakcje mogą być zawieszane, tylko jeśli **nie** zawierają następujących wierszy:

- Aktywne wiersze płatności
- Wiersze kart upominkowych (do wystawienia karty upominkowej lub dodania salda na karcie upominkowej)

Wstrzymana transakcja nie ma wpływu na informacje o sprzedaży ani dostępność zapasów w sklepie.

### <a name="resume-a-suspended-transaction"></a>Usuwanie wstrzymanej transakcję

Zawieszone transakcje mogą być wywoływane i wznawiane w tym samym sklepie przez dowolnego użytkownika, który ma wystarczające uprawnienia, i który ma układ zawierający operację **Wywołaj transakcję**.

Aby szybko i łatwo wznowić zawieszoną transakcję, zeskanuj kod kreskowy na wydrukowanym dokumencie podczas przeglądania listy transakcji z operacji **Wywołaj transakcję**.

### <a name="considerations-for-offline-mode"></a>Uwagi dotyczące trybu offline

- Transakcji zawieszonych w punkcie sprzedaży w trybie online nie można wznowić w trybie offline, ponieważ dane nie są synchronizowane z bazą danych offline.
- Jeśli transakcja została zawieszona gdy punkt sprzedaży działał w trybie offline, można ją wznowić w trybie offline, pod warunkiem że punkt sprzedaży nie został przełączony do trybu online od czasu zawieszenia transakcji. Kiedy punkt sprzedaży zostanie przełączony do trybu online, dane dotyczące zawieszonych transakcjach są przenoszone do bazy danych online i usuwane z bazy danych offline. W związku z tym transakcje można wznowić tylko w trybie online. Jeśli punkt sprzedaży zostanie przełączony z powrotem do trybu offline, nie będzie można wznowić tej zawieszonej transakcji, ponieważ została już usunięta z bazy danych offline.

### <a name="void-a-suspended-transaction"></a>Unieważnienie zawieszonej transakcji

Można unieważnić zawieszone transakcje przez ich wywołanie a następnie wykonanie operacji **Unieważnij transakcję** lub przez wybranie transakcji z listy **Wycofaj transakcję** i wybranie opcji **Unieważnij**na pasku aplikacji. Ewentualnie można skonfigurować sklepu do wyświetlania użytkownikom monitów o unieważnienie zawieszonych transakcji w chwili kończenia zmiany.
