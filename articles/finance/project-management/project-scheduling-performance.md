---
title: Planowanie wydajności zasobów projektu
description: Ten temat zawiera informacje o sposobach zwiększania wydajności planowania zasobów dla dużej liczby projektów.
author: Yowelle
manager: AnnBe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 10.0.14
ms.search.validFrom: 2020-09-01
ms.openlocfilehash: 988fc83230f08a6534caa7c37784757d73c1cc12
ms.sourcegitcommit: 241ada0945c72d769eaa70ae35aedbb6a3233fdf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/02/2020
ms.locfileid: "3760639"
---
# <a name="project-resource-scheduling-performance"></a>Planowanie wydajności zasobów projektu

[!include [banner](../includes/banner.md)]
[!include [banner](../includes/preview-banner.md)]


Problemy z wydajnością związane z planowaniem zasobów mogą wystąpić, gdy liczba projektów będzie liczona w tysiącach. Aby poprawić wydajność planowania zasobów, dostępna jest funkcja umożliwiająca użytkownikom skrócenie czasu niezbędnego do uruchomienia formularza dostępności zasobu. Powoduje to usunięcie procesu synchronizacji dyspozycyjności zasobów i zastosowanie tabeli **ResProjectResource** w celu przyspieszenia wyszukiwania zasobów. Zauważ, że tabela **ResRollup** nie będzie już używana.

> [!IMPORTANT]
> Jeśli istnieje zależność od procesu synchronizacji zdolności produkcyjnych zasobów lub tabeli **ResProjectResource**, nie należy stosować tej funkcji.

## <a name="enable-resource-scheduling-performance-enhancement"></a>Włączanie rozszerzania wydajności planowania zasobów
Aby włączyć rozszerzanie wydajności planowania zasobów, należy wykonać następujące kroki:

1. Przejdź do funkcji **Zarządzanie funkcjami** > **Wszystko**, a na liście funkcji znajdź pozycję **Włącz funkcję zwiększania wydajności planowania zasobów projektu**.
2. Wybierz **Włącz teraz**.

> [!NOTE]
> Jeśli nie możesz odnaleźć tej funkcji na liście, wybierz opcję **Sprawdź dostępność aktualizacji**, aby odświeżyć listę.

3. Odśwież przeglądarkę, a następnie przejdź do obszaru **Zarządzanie projektami i księgowanie** > **Okresowe** > **Zasoby projektu** > **Synchronizuj kalendarze zasobów między wszystkimi firmami**.
4. Ustaw wartość **Usuń istniejące rekordy zdolności produkcyjnych** na **Tak**, aby usunąć poprzednie dane. Jeśli chcesz generować przyrostowe dane, wybierz wartość **Nie**.
5. W polu **Kod okresu** wybierz okres, dla którego mają zostać wygenerowane dane. W przypadku wybrania kodu okresu nie trzeba definiować daty rozpoczęcia i zakończenia.
6. Jeśli pole **Kod okresu** pozostanie puste, w celu wygenerowania danych wybierz określone daty rozpoczęcia i zakończenia.
7. Kliknij przycisk **OK**.

 > [!NOTE]
 > Spowoduje to dystrybuowanie ogólnych danych do tabeli **ResCalendarCapacity** we wszystkich firmach w danym środowisku, więc zadanie wsadowe należy uruchomić tylko w jednej firmie. Dane w tym zadaniu wsadowym są potrzebne do obliczenia zdolności produkcyjnych zasobu za pośrednictwem skojarzonego z nim kalendarza.

8. Przejdź do obszaru **Zarządzanie projektami i księgowanie** > **Okresowe** > **Zasoby projektu** > **Wypełnij zasoby projektu we wszystkich firmach**, a następnie kliknij przycisk **OK**. To jest skrypt uaktualnienia danych dla ogólnych danych w tabelach **ResProjectResource**, **ResCalendarDateTimeRange** i **ResEffectiveDateTimeRange**. Wartości pola **PSAPRojSchedRole.RootActivity** również zostaną zaktualizowane. Jeśli nie zostanie uruchomiony, podczas próby wykonania operacji planowania zasobów zostanie wyświetlone ostrzeżenie.
 
## <a name="turn-off-resource-scheduling-performance-enhancement"></a>Wyłączanie rozszerzania wydajności planowania zasobów

1. Przejdź do funkcji **Zarządzanie funkcjami** > **Wszystko**, a na liście funkcji znajdź **Włącz funkcję zwiększania wydajności planowania zasobów projektu**.
2. Wybierz funkcję, a następnie wybierz **Wyłącz**.
3. Odśwież przeglądarkę.
4. Wybierz kolejno opcje **Zarządzanie projektami i ich księgowanie** > **Okresowe** > **Synchronizacja zdolności produkcyjnych** > **Synchronizuj zestawienia zdolności produkcyjnych zasobów**.
5. Na stronie **Synchronizacja zdolności produkcyjnych** ustaw dla opcji **Usuń istniejące rekordy zdolności produkcyjnych** wartość **Tak**, aby usunąć poprzednie dane. Jeśli chcesz generować przyrostowe dane, wybierz wartość **Nie**.
6. W polu **Kod okresu** wybierz okres, dla którego mają zostać wygenerowane dane. W przypadku wybrania kodu okresu nie trzeba definiować daty rozpoczęcia i zakończenia.
7. Jeśli pole **Kod okresu** pozostanie puste, w celu wygenerowania danych wybierz określone daty rozpoczęcia i zakończenia.
8. Kliknij przycisk **OK**.

> [!NOTE]
> Spowoduje to dystrybuowanie ogólnych danych do tabeli **ResRollup** we wszystkich firmach w danym środowisku, więc zadanie wsadowe należy uruchomić tylko w jednej firmie. To zadanie wsadowe jest wymagane w przypadku wszystkich widoków **Dostępności zasobów**. Jeśli to zadanie wsadowe nie zostanie uruchomione, dane **ResRollup** będą generowane na bieżąco, co może być czasochłonne.
