---
title: Anulowanie zadania planowania głównego
description: W tym artykule wyjaśniono, jak anulować aktywne planowanie pracy, gdy używana jest wbudowana funkcja planowania.
author: t-benebo
ms.date: 05/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace, ReqProcessList
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-12-16
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6a9667be9921fdde7e1ca5de68c7f51d48905ac8
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860791"
---
# <a name="cancel-a-master-planning-job"></a>Anulowanie zadania planowania głównego

[!include [banner](../includes/banner.md)]

W aplikacji Microsoft Dynamics 365 Supply Chain Management istnieje wiele opcji anulowania zadania planowania głównego. Na przykład można anulować zadanie planowania głównego, jeśli zostało uruchomiony przez pomyłkę lub działa dłużej niż oczekiwano i chcesz je zakończyć. Najlepszym sposobem anulowania zadania planowania jest przejście na stronę **niedokończonych procesów planowania**. Alternatywne opcje ze stron **Zadania wsadowe** i **Rozszerzone zadania wsadowe** powinny być używane tylko wtedy, gdy anulowanie zadania planowania głównego na stronie **Nieukończone procesy planowania** nie zostało ukończone w ciągu kilku minut.

## <a name="preferred-cancel-option"></a>Preferowana opcja anulowania
### <a name="cancel-master-planning-job-from-unfinished-planning-processes-page"></a>Anulowanie zadania planowania głównego ze strony **Nieukończone procesy planowania**
1. Przejdź do pozycji **Planowanie główne > Zapytania i raporty > Planowanie główne > Nieukończone procesy planowania**.
2. Wybierz wiersz z procesem planowania, który chcesz anulować.
3. Kliknij **Anuluj**.

## <a name="additional-cancel-options"></a>Dodatkowe opcje anulowania
Te opcji powinny być używane tylko, jeśli anulowanie zadania planowania głównego na stronie **Nieukończone procesy planowania** nie zostały ukończone w ciągu kilku minut.

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a>Usuwanie zadania planowania głównego ze strony **Zadania wsadowe**
1. Otwórz **Administracja systemu > Zapytania > Zadania wsadowe**.
2. Wybierz wiersz z zadaniem planowania, które chcesz usunąć.
3. Kliknij przycisk **Usuń**.

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a>Przerywanie zadania dla zadania planowania głównego ze strony **Rozszerzone zadania wsadowe**
1. Otwórz **Administracja systemu > Zapytania > Zadania wsadowe**.
2. Jeśli identyfikator zadania nie jest wyświetlany na liście, kliknij pozycję **Przełącz do formularza rozszerzonego**, w przeciwnym razie przejdź do następnego kroku.
3. Otwórz zadanie wsadowe. Kliknij **identyfikator zadania** dla zadania wsadowego z zadaniami, które chcesz zakończyć.
4. W obszarze **Zadania wsadowe** wybierz zadania do zakończenia.
5. Kliknij pozycję **Zmień stan**, wybierz pozycję **Anuluj** i kliknij przycisk **OK**.
6. Na skróconej karcie **Zadania wsadowe** kliknij pozycję **Przerwij**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]