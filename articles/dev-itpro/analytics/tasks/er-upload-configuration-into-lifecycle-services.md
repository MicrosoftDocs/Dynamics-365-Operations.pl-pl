---
title: ER Przekazywanie konfiguracji do usługi Lifecycle Services
description: W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfiguracji raportowania elektronicznego (ER) i przekazać ją do usługi Microsoft Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, ERSolutionCreateDropDialog, ERDataModelDesigner, ERDataModelContentsItemCreationDialog, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 19ae8820e5d4a798a5789e9632edb431fe9fede4
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "1551120"
---
# <a name="er-upload-a-configuration-into-lifecycle-services"></a>ER Przekazywanie konfiguracji do usługi Lifecycle Services

[!include [task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik w roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć nową konfiguracji raportowania elektronicznego (ER) i przekazać ją do usługi Microsoft Lifecycle Services (LCS).

W tym przykładzie utworzysz konfigurację dla przykładowej firmy Litware, Inc. i przekażesz ją do usługi LCS. Podane kroki można wykonać w dowolnej firmie, ponieważ konfiguracje ER są współużytkowane przez wszystkie firmy. Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”. W celu wykonania tych kroków jest również wymagany dostęp do usługi LCS.

1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Wybierz firmę „Litware, Inc.” i ustaw ją jako aktywną.
3. Kliknij opcję Konfiguracje.

## <a name="create-a-new-data-model-configuration"></a>Tworzenie nowej konfiguracji modelu danych
1. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
    * Utworzysz konfigurację, która zawiera przykładowy model danych dla dokumentów elektronicznych. Ta konfiguracja modelu danych zostanie później przekazana do usługi LCS.  
2. W polu Nazwa wpisz „Konfiguracja przykładowego modelu”.
    * Konfiguracja przykładowego modelu  
3. W polu Opis wpisz „Konfiguracja przykładowego modelu”.
    * Konfiguracja przykładowego modelu  
4. Kliknij przycisk Utwórz konfigurację.
5. Kliknij opcję Projektant modeli.
6. Kliknij przycisk Nowy.
7. W polu Nazwa wpisz „Punkt wejścia”.
    * Punkt wejścia  
8. Kliknij przycisk Dodaj.
9. Kliknij przycisk Zapisz.
10. Zamknij stronę.
11. Kliknij przycisk Zmień stan.
12. Kliknij przycisk Wykonaj.
13. Kliknij przycisk OK.

## <a name="register-a-new--repository"></a>Rejestrowanie nowego repozytorium
1. Zamknij stronę.
2. Kliknij Repozytoria.
    * Dzięki temu można otworzyć listę repozytoriów dostawcy konfiguracji firmy Litware, Inc.  
3. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
    * Dzięki temu można dodać nowe repozytorium.  
4. W polu Typ repozytorium konfiguracji zaznacz usługę LCS.
5. Kliknij opcję Utwórz repozytorium.
6. W polu Projekt wprowadź lub wybierz wartość.
    * Wybierz żądany projekt usługi LCS. Trzeba mieć dostęp do projektu.  
7. Kliknij przycisk OK.
    * Wypełnij wpis nowego repozytorium.  
8. Na liście oznacz wybrany wiersz.
    * Wybierz rekord repozytorium usługi LCS.  
    * Należy zwrócić uwagę, że zarejestrowane repozytorium jest oznaczone przez bieżącego dostawcę, co oznacza, że tylko konfiguracje posiadane przez tego dostawcę mogą być umieszczane w tym repozytorium i w związku z tym przekazywane do wybranego projektu usługi LCS.  
9. Kliknij przycisk Otwórz.
    * Otwórz repozytorium, aby wyświetlić listę konfiguracji raportowania elektronicznego. Będzie ona pusta, jeśli ten projekt nie był jeszcze używany w udostępnianiu konfiguracji raportowania elektronicznego.  
10. Zamknij stronę.
11. Zamknij stronę.

## <a name="upload-configuration-into-lcs"></a>Przekazywanie konfiguracji do usługi LCS
1. Kliknij opcję Konfiguracje.
2. W drzewie zaznacz element „Konfiguracja przykładowego modelu”.
    * Zaznacz utworzone konfiguracje, które zostały już ukończone.  
3. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zaznacz wersję wybranej konfiguracji ze stanem „Zakończono”.  
4. Kliknij przycisk Zmień stan.
5. Kliknij przycisk Udostępnij.
    * Po opublikowaniu konfiguracji w usłudze LCS stan konfiguracji ulegnie zmianie z „Zakończono” na „Udostępniono”.  
6. Kliknij przycisk OK.
7. Na liście znajdź i zaznacz odpowiedni rekord.
    * Zaznacz wersję konfiguracji o stanie „Udostępniono”.  
    * Należy zauważyć, że stan wybranej wersji został zmieniony z „Zakończono” na „Udostępniono”.  
8. Zamknij stronę.
9. Kliknij Repozytoria.
    * Dzięki temu można otworzyć listę repozytoriów dostawcy konfiguracji firmy Litware, Inc.  
10. Kliknij przycisk Otwórz.
    * Zaznacz repozytorium usługi LCS i je otwórz.  
    * Należy zwrócić uwagę, że wybrana konfiguracja jest wyświetlana jako element zawartości wybranego projektu usługi LCS.  
    * Otwórz usługę LCS ze strony https://lcs.dynamics.com. Otwórz projekt, który został wcześniej użyty do zarejestrowania repozytorium, otwórz bibliotekę elementów zawartości tego projektu, a następnie rozwiń zawartość elementu zawartości typu „Konfiguracja GER” — przekazana konfiguracja raportowania elektronicznego będzie dostępna. Należy zauważyć, że przekazaną konfigurację usługi LCS można zaimportować do innego wystąpienia programu Microsoft Dynamics 365 for Finance and Operations Enterprise Edition, jeśli dostawcy mają dostęp do tego projektu usługi LCS.  

