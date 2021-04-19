---
title: Automatyczna aktualizacja liczników składników majątku
description: W tym temacie opisano automatyczną aktualizację liczników składników majątku w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f15aea2f867de6f0bcf01ecfd046efc44581a1ec
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/01/2021
ms.locfileid: "5820449"
---
# <a name="automatic-update-of-asset-counters"></a>Automatyczna aktualizacja liczników zasobów

[!include [banner](../../includes/banner.md)]

Aby uzyskać informacje dotyczące ręcznej rejestracji liczników składników majątku, zobacz [Ręczna aktualizacja liczników składnika majątku](../work-orders/manual-update-of-asset-counters.md). Aby uzyskać informacje na temat sposobu konfigurowania liczników składnika majątku, zobacz [Liczniki](../setup-for-objects/counters.md).

Wartości licznika mogą być także automatycznie aktualizowane z poziomu rejestracji produkcji na podstawie godzin produkcji lub ilości produkcji (czyli wytwarzanej ilości). Ta aktualizacja jest przeprowadzana na stronie **Aktualizowanie liczników składnika majątku**. Można zaktualizować jeden lub kilka składników majątku, ustawiając jeden parametr **Od dnia**. Ten parametr służy do określania daty rozpoczęcia rejestracji produkcji (godzin produkcji lub ilości produkcji). Mówiąc inaczej, określa on datę, od której powinny być aktualizowane wartości liczników.

Wszystkie składniki majątku, które są związane z zasobem *i* mają liczniki składników majątku skonfigurowane do aktualizacji na podstawie godzin produkcji lub ilości produkcji, zostaną uwzględnione w aktualizacji automatycznej. Zostaną utworzone nowe wartości liczników.

W przypadku liczników opartych na ilości produkcji licznik uwzględnia ilość dobrych i ilość wadliwych towarów, które są rejestrowane. Jeśli jednostka używana do rejestrowania ilości produkcji różni się od jednostki używanej w liczniku, ilość jest konwertowana tak, aby odpowiadała jednostce licznika.

Jak wspomniano powyżej, liczniki automatyczne mogą być aktualizowane na podstawie rejestracji produkcji. Dlatego składnik majątku, dla którego mają być automatycznie aktualizowane liczniki, musi być powiązany z zasobem (maszyną). Jeśli w zasobie zostały zarejestrowane wyprodukowane ilości lub godziny produkcji, można zaktualizować powiązane liczniki składnika majątku.

1. Wybierz pozycję **Zarządzanie składnikami majątku** > **Okresowe** > **Składniki majątku** > **Aktualizuj liczniki składnika majątku**.

2. W polu **Od dnia** wybierz datę początkową automatycznej aktualizacji.

    >[!NOTE]
    >Datą w tym polu jest datą „pracy w toku” od **Transakcje marszruty** (**Kontrola produkcji** > **Zapytania i raporty** > **Produkcja** > **Transakcje marszruty** > **Data fizycznej transakcji** pole).

3. Na skróconej karcie **Rekordy do uwzględnienia** można wybrać określone składniki majątku, typy składników majątku lub zasoby do automatycznej aktualizacji. Wybierz pozycję **Filtr** i wybierz odpowiednie opcje.

4. Na skróconej karcie **uruchom w tle** w razie potrzeby możesz skonfigurować automatyczną aktualizację jako zadanie wsadowe.

    Na poniższej ilustracji przedstawiono przykład okna dialogowego **Aktualizowanie liczników składnika majątku**.

    ![Rysunek 1](media/12-work-orders.png)

5. Kliknij przycisk **OK**. 

Po zakończeniu aktualizacji licznika składników majątku można przejrzeć rejestracje liczników powiązane z danym składnikiem majątku na stronie **Liczniki składników majątku**. Wybierz pozycję **Zarządzanie składnikami majątku** > **Wspólne** > **Składniki majątku** > **Wszystkie składniki majątku**, wybierz składnik majątku, a następnie w okienku akcji na karcie **Składnik majątku**, w grupie **Zapobiegawcze** wybierz pozycję **Liczniki**.

Na stronie **Zagregowana wartość składnika majątku** można uzyskać przegląd najnowszej rejestracji przeprowadzonej dla wszystkich typów licznika we wszystkich składnikach majątku. Wybierz pozycję **Zarządzanie składnikami majątku** > **Zapytania** > **Składniki majątku** > **Zagregowana wartość składnika majątku**. Ta strona przypomina stronę **Liczniki składników majątku**, ale nie można dodawać ani edytować rejestracji. Służy ona tylko do przeglądu.

Na poniższej ilustracji przedstawiono przykład strony **Zagregowana wartość składnika majątku**.

![Rysunek 2](media/13-work-orders.png)

Należy uwzględnić następujące informacje:

- W dalszym ciągu możesz tworzyć ręczne rejestracje wartości licznika dla typów licznika, które są automatycznie aktualizowane. Aby uzyskać więcej informacji, zobacz [Ręczna aktualizacja liczników składnika majątku](../work-orders/manual-update-of-asset-counters.md).

- Możesz konfigurować liczniki powiązane z innym licznikiem. W tym przypadku jeśli licznik jest aktualizowany, powiązane liczniki są automatycznie aktualizowane w tym samym czasie. Aby uzyskać więcej informacji na temat sposobu konfigurowania powiązanych liczników, zobacz [Liczniki](../setup-for-objects/counters.md).



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]