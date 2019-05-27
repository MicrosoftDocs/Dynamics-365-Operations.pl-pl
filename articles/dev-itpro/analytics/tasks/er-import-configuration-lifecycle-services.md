---
title: ER Importowanie konfiguracji z usługi Lifecycle Services
description: W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może zaimportować nową wersję konfiguracji raportowania elektronicznego (ER) z usługi Microsoft Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable,  ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 036d7e7e3f79e0945d6fef866a30edd41e688c07
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551329"
---
# <a name="er-import-a-configuration-from-lifecycle-services"></a>ER Importowanie konfiguracji z usługi Lifecycle Services

[!include [task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może zaimportować nową wersję konfiguracji raportowania elektronicznego (ER) z usługi Microsoft Lifecycle Services (LCS).

W tym przykładzie wybierzesz żądaną wersję konfiguracji raportowania elektronicznego dla przykładowej firmy Litware, Inc. i zaimportujesz ją. Podane kroki można wykonać w dowolnej firmie, ponieważ konfiguracje ER są współużytkowane przez wszystkie firmy. Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Przekazywanie konfiguracji ER do usługi Lifecycle Services”. W celu wykonania tych kroków jest również wymagany dostęp do usługi LCS.

1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Kliknij opcję Konfiguracje.

## <a name="delete-a-shared-version-of-data-model-configuration"></a>Usuwanie udostępnionej wersji konfiguracji modelu danych
1. W drzewie zaznacz element „Konfiguracja przykładowego modelu”.
    * Pierwsza wersja konfiguracji przykładowego modelu danych została utworzona i opublikowana w usłudze LCS podczas procedury „Przekazywanie konfiguracji ER do usługi Lifecycle Services”. W tej procedurze usuniesz tę wersję konfiguracji raportowania elektronicznego. Ta wersja konfiguracji przykładowego modelu danych zostanie zaimportowana później z usługi LCS.  
2. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zaznacz wersję tej konfiguracji mającą stan „Udostępniono”. Ten stan wskazuje, że konfiguracja została opublikowana w usłudze LCS.  
3. Kliknij przycisk Zmień stan.
4. Kliknij opcję Nie kontynuuj.
    * Zmień stan wybranej wersji z „Udostępniono” na „Zaprzestano”, aby ją udostępnić do usunięcia.  
5. Kliknij przycisk OK.
6. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zaznacz wersję tej konfiguracji mającą stan „Zaprzestano”.  
7. Kliknij przycisk Usuń.
8. Kliknij przycisk Tak.
    * Należy zauważyć, że jest dostępna tylko wersja robocza 2 wybranej konfiguracji przykładowego modelu danych.  
9. Zamknij stronę.

## <a name="import-a-shared-version-of-data-model-configuration-from-lcs"></a>Importowanie udostępnionej wersji konfiguracji modelu danych z usługi LCS
1. Na liście oznacz wybrany wiersz.
    * Otwórz listę repozytoriów dostawcy konfiguracji, czyli firmy firmy Litware, Inc.  
2. Kliknij Repozytoria.
3. Kliknij przycisk Otwórz.
    * Zaznacz repozytorium usługi LCS i je otwórz.  
4. Na liście oznacz wybrany wiersz.
    * Na liście wersji zaznacz pierwszą wersję konfiguracji przykładowego modelu.  
5. Kliknij przycisk Importuj.
6. Kliknij przycisk Tak.
    * Potwierdź import wybranej wersji z usługi LCS.  
    * Należy zauważyć, że komunikat informacyjny (nad formularzem) potwierdza pomyślne ukończenia importu wybranej wersji.  
7. Zamknij stronę.
8. Zamknij stronę.
9. Kliknij opcję Konfiguracje.
10. W drzewie zaznacz element „Konfiguracja przykładowego modelu”.
11. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zaznacz wersję tej konfiguracji mającą stan „Udostępniono”.  
    * Należy zauważyć, że teraz jest również dostępna udostępniona wersja 1 wybranej konfiguracji przykładowego modelu danych.  

