---
title: Automatyczna aktualizacja liczników składników majątku
description: W tym temacie opisano automatyczną aktualizację liczników składników majątku w module Zarządzanie składnikami majątku.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 97e6912cd37d6f82d8bf022141f04645a3364ee1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875847"
---
# <a name="automatic-update-of-asset-counters"></a>Automatyczna aktualizacja liczników składników majątku

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

W poprzedniej sekcji opisano ręczną rejestrację liczników składników majątku. Konfiguracja liczników składnika majątku jest opisana w [Liczniki](../setup-for-objects/counters.md).

Wartości licznika mogą być także automatycznie aktualizowane na podstawie rejestracji produkcji na podstawie godzin produkcji lub ilości produkcji. Odbywa się to w **Aktualizuj liczniki składnika majątku**. Można zaktualizować jeden lub kilka składników majątku, wstawiając jeden parametr **Od dnia**. Ten parametr określa datę początkową rejestracji produkcji (liczba godzin lub ilość wyprodukowana), czyli datę początkową, od której powinny być aktualizowane wartości liczników.

Wszystkie środki trwałe, które są związane z zasobem *i* mają liczniki składnika majątku, które są skonfigurowane do aktualizacji na podstawie ilości wyprodukowanej lub godzin produkcji, zostaną uwzględnione w aktualizacji automatycznej i zostaną utworzone nowe wartości liczników.

W przypadku liczników na podstawie ilości produkcji, ilość dobrych towarów, a także zarejestrowana ilość wadliwych towarów jest uwzględniana w liczniku. Jeśli jednostka użyta do zarejestrowania ilości produkcji różni się od jednostki użytej w liczniku, ilość jest konwertowana na odpowiadającą jednostce licznika.

Jak wspomniano powyżej, liczniki automatyczne mogą być aktualizowane na podstawie rejestracji produkcji. Dlatego składnik majątku, dla którego mają być automatycznie aktualizowane liczniki, musi być powiązany z zasobem (maszyną). Poniższe opisy zawierają przegląd ustawień i przetwarzania zleceń produkcyjnych (w module **Kontrola produkcji**), które są używane jako podstawa automatycznej aktualizacji liczników składnika majątku w module **Zarządzanie składnikami majątku**.

Jeśli w zasobie zostały zarejestrowane wyprodukowane ilości lub godziny produkcji, można zaktualizować powiązane liczniki składnika majątku.

1. Kliknij **Zarządzanie składnikami majątku** > **Okresowe** > **Składniki majątku** > **Aktualizuj liczniki składnika majątku**.

2. Wybierz datę początkową automatycznej aktualizacji w polu **Od dnia**.

>[!NOTE]
>Datą w tym polu jest datą „pracy w toku” od **Transakcje marszruty** (**Kontrola produkcji** > **Zapytania i raporty** > **Produkcja** > **Transakcje marszruty** > **Data fizycznej transakcji** pole).

3. Jeśli chcesz wybrać określone zasoby, typy składników majątku lub zasoby dla aktualizacji automatycznych, kliknij przycisk **Filtruj** na skróconej karcie **Rekordy do uwzględnienia** i dokonaj odpowiednich wyborów.

4. W razie potrzeby możesz skonfigurować automatyczną aktualizację jako zadanie wsadowe na skróconej karcie **Uruchom w tle**.

![Rysunek 1](media/12-work-orders.png)

5. Kliknij przycisk **OK**. Po wykonaniu aktualizacji licznika składnika majątku można zobaczyć rejestracje liczników powiązanych ze składnikiem majątku w **Liczniki składnika majątku** (**Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku** > wybierz składnik majatku > przycisk **Licznik**).

W **Sumy licznika składnika majątku** można uzyskać przegląd najnowszej rejestracji wszystkich typów licznika na wszystkich składnikach majątku. Kliknij **Zarządzanie składnikami majątku** > **Zapytania** > **Składniki majątku** > **Zagregowana wartość składnika majątku**. Widok jest bardzo podobny do **Liczniki składnika majątku**, ale nie można dodawać ani edytować rejestracji w **Zagregowana wartość składnika majątku**. Służy tylko do przeglądu.

![Rysunek 2](media/13-work-orders.png)


- Nadal istnieje możliwość tworzenia ręcznych rejestracji wartości licznika dla typów licznika, które są automatycznie aktualizowane. Aby uzyskać więcej informacji, zobacz sekcję „Ręczna aktualizacja liczników składnika majątku”
- Istnieje możliwość skonfigurowania liczników powiązanych z innym licznikiem, co oznacza, że po zaktualizowaniu licznika powiązane liczniki są automatycznie aktualizowane w tym samym czasie. Należy zapoznać się z tematem [Liczniki](../setup-for-objects/counters.md), aby zobaczyć konfigurację powiązanych liczników.
