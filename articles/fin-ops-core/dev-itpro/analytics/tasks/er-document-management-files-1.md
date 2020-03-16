---
title: ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 1 — Przygotowanie modelu danych)
description: W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c6085f2f06fb374887d504c332a34705f0fd9e99
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/12/2020
ms.locfileid: "3042834"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a>ER Używanie plików zarządzania dokumentami w danych wyjściowych formatu (Część 1 — Przygotowanie modelu danych)

[!include [task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby w danych wyjściowych raportowania elektronicznego używać plików zarządzania danymi (załączników). Kroki można wykonać na danych dowolnej firmy.

Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.

Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Uzyskiwanie dostępu do listy konfiguracji dostarczanej przez firmę Microsoft
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.

    Upewnij się, że dostawca „Litware, Inc.” jest dostępny i oznaczony jako aktywny.  

2. Zaznacz dostawcę „Litware, Inc.”.  
3. Kliknij Repozytoria.

    Jeśli repozytorium typu „Zasoby operacyjne” już istnieje, należy pominąć pozostałe kroki bieżącego zadania podrzędnego.  

4. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
5. W polu Typ repozytorium konfiguracji wprowadź wartość „Zasoby operacyjne”.
6. Kliknij opcję Utwórz repozytorium.
7. Kliknij przycisk OK.

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a>Pobieranie konfiguracje modelu faktur sprzedaży dostarczonych przez firmę Microsoft
1. Kliknij przycisk Pokaż filtry.
2. Zastosuj następujące filtry: w polu „Nazwa” wprowadź wartość filtru „Zasoby operacyjne”, używając operatora filtru „zaczyna się od”; w polu „Opis” wprowadź wartość filtru "", używając operatora filtru „zaczyna się od”
3. Kliknij przycisk Pokaż filtry.
4. Kliknij przycisk Otwórz.
5. W drzewie zaznacz element „Model faktur sprzedaży”.

    Zaznacz konfigurację modelu „Model faktur sprzedaży”, aby ją zaimportować.  

6. Kliknij przycisk Importuj.

    Kliknij przycisk Importuj dla wersji 1 wybranej konfiguracji.  

7. Kliknij przycisk Tak.
8. Zamknij stronę.
9. Zamknij stronę.
10. Kliknij opcję Konfiguracje raportowania.
11. W drzewie zaznacz element „Model faktur sprzedaży”.

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a>Utwórz pochodny model w celu umożliwienia dostępu do plików zarządzania dokumentami.
Utworzysz własną konfigurację modelu faktur sprzedaży na podstawie konfiguracji dostarczonej przez firmę Microsoft. Użyjesz tej konfiguracji w celu zaimplementowania dostępu do plików zarządzania dokumentami oraz udostępnienia ich dla dokumentów elektronicznych, które zostaną utworzone na podstawie tego modelu.  
1. Kliknij przycisk Utwórz konfigurację, aby otworzyć rozwijane okno dialogowe.
2. W polu Nowy wprowadź wyrażenie „Pochodzi od nazwy: Model faktur sprzedaży, Microsoft”.
3. W polu Nazwa wpisz „Model faktur sprzedaży (niestandardowy)”.
4. Kliknij przycisk Utwórz konfigurację.

