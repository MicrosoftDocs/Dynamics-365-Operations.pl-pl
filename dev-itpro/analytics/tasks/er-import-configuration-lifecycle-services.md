--- 
title: "Importowanie konfiguracji z usługi Lifecycle Services na potrzeby raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może zaimportować nową wersję konfiguracji raportowania elektronicznego (ER) z usługi Microsoft Lifecycle Services (LCS)."
author: NickSelin
manager: AnnBe
ms.date: 05/13/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ab453d3ee44e206aea148de8dc3b428dc5056576
ms.contentlocale: pl-pl
ms.lasthandoff: 07/27/2017

---
# <a name="import-a-configuration-from-lifecycle-services-for-electronic-reporting-er"></a>Importowanie konfiguracji z usługi Lifecycle Services na potrzeby raportowania elektronicznego (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


