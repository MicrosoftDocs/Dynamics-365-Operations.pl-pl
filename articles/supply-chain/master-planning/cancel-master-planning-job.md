---
title: Anulowanie zadania utworzonego przy użyciu przestarzałego aparatu planowania głównego
description: W tym artykule wyjaśniono, jak anulować aktywne zadanie planowania, które wykorzystuje przestarzały silnik planowania głównego.
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
ms.openlocfilehash: 7b71a43f407050dccb7550db7c4b6a98a596d589
ms.sourcegitcommit: 491ab9ae2b6ed991b4eb0317e396fef542d3a21b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/03/2022
ms.locfileid: "9740885"
---
# <a name="cancel-a-job-that-was-created-using-the-deprecated-master-planning-engine"></a>Anulowanie zadania utworzonego przy użyciu przestarzałego aparatu planowania głównego

[!include [banner](../includes/banner.md)]

Istnieje wiele opcji anulowania zadania, które zostało utworzone przy użyciu przestarzałego silnika planowania głównego. Na przykład można anulować zadanie planowania głównego, jeśli zostało uruchomiony przez pomyłkę lub działa dłużej niż oczekiwano i chcesz je zakończyć.

Najlepszym sposobem anulowania zadania planowania jest przejście na stronę **niedokończonych procesów planowania**. Alternatywne opcje ze stron **Zadania wsadowe** i **Rozszerzone zadania wsadowe** powinny być używane tylko wtedy, gdy anulowanie zadania planowania głównego na stronie **Nieukończone procesy planowania** nie zostało ukończone w ciągu kilku minut.

## <a name="preferred-cancel-option"></a>Preferowana opcja anulowania

### <a name="cancel-master-planning-job-from-the-unfinished-planning-processes-page"></a>Anulowanie zadania planowania głównego ze strony Nieukończone procesy planowania

1. Przejdź do pozycji **Planowanie główne > Zapytania i raporty > Planowanie główne > Nieukończone procesy planowania**.
2. Wybierz wiersz z procesem planowania, który chcesz anulować.
3. Wybierz **Anuluj**.

## <a name="additional-cancel-options"></a>Dodatkowe opcje anulowania

Te opcji powinny być używane tylko, jeśli anulowanie zadania planowania głównego na stronie **Nieukończone procesy planowania** nie zostały ukończone w ciągu kilku minut.

### <a name="delete-master-planning-job-from-the-batch-jobs-page"></a>Usuwanie zadania planowania głównego ze strony **Zadania wsadowe**

1. Otwórz **Administracja systemu > Zapytania > Zadania wsadowe**.
2. Wybierz wiersz z zadaniem planowania, które chcesz usunąć.
3. Wybierz opcję **Usuń**.

### <a name="abort-master-planning-job-task-from-the-batch-jobs-enhanced-page"></a>Przerywanie zadania dla zadania planowania głównego ze strony **Rozszerzone zadania wsadowe**

1. Otwórz **Administracja systemu > Zapytania > Zadania wsadowe**.
2. Jeśli identyfikator zadania nie jest wyświetlany na liście, kliknij pozycję **Przełącz do formularza rozszerzonego**, w przeciwnym razie przejdź do następnego kroku.
3. Otwórz zadanie wsadowe. Wybierz **identyfikator zadania** dla zadania wsadowego z zadaniami, które chcesz zakończyć.
4. W obszarze **Zadania wsadowe** wybierz zadania do zakończenia.
5. Wybierz pozycję **Zmień stan**, wybierz pozycję **Anuluj** i kliknij przycisk **OK**.
6. Na skróconej karcie **Zadania wsadowe** kliknij pozycję **Przerwij**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]