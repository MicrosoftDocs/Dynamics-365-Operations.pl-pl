--- 
title: "Tworzenie formatu służącego do zliczania i sumowania na potrzeby raportowania elektronicznego (ER)"
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych."
author: NickSelin
manager: AnnBe
ms.date: 11/02/2017
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
ms.sourcegitcommit: 5d4f57ae2a309d9e15c1afe60c3e91d7d7eb3870
ms.openlocfilehash: 3c4ae958a03d4681a85f5b83d81fe64b9ac99cf5
ms.contentlocale: pl-pl
ms.lasthandoff: 11/02/2017

---
# <a name="create-format-for-counting-and-summing-for-electronic-reporting-er"></a>Tworzenie formatu służącego do zliczania i sumowania na potrzeby raportowania elektronicznego (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych. Kroki można wykonać na danych dowolnej firmy.

Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.

Ta procedura dotyczy funkcji, która została dodana w programie Dynamics 365 for Operations w wersji 1611.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Uzyskiwanie dostępu do listy konfiguracji dostarczanej przez firmę Microsoft
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
    * Upewnij się, że dostawca „Litware, Inc.” jest dostępny i oznaczony jako aktywny.  
2. Zaznacz dostawcę „Litware, Inc.”.  
3. Kliknij Repozytoria.
    * Jeśli repozytorium typu „Zasoby operacyjne” już istnieje, należy pominąć pozostałe kroki bieżącego zadania podrzędnego.  
4. Kliknij przycisk Dodaj, aby otworzyć rozwijane okno dialogowe.
5. W polu Typ repozytorium konfiguracji wprowadź wartość „Zasoby operacyjne”.
6. Kliknij opcję Utwórz repozytorium.
7. Kliknij przycisk OK.

## <a name="get-the-intrastat-configurations-provided-by-microsoft"></a>Pobieranie konfiguracji Intrastat dostarczanych przez firmę Microsoft
1. Kliknij przycisk Otwórz.
2. W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)”.
3. Kliknij przycisk Importuj.
    * Kliknij przycisk Importuj dla wersji 1.1 wybranej konfiguracji.  
4. Kliknij przycisk Tak.
5. Zamknij stronę.
6. Zamknij stronę.
7. Kliknij opcję Konfiguracje raportowania.
8. W drzewie rozwiń węzeł „Model Intrastat”.
9. W drzewie zaznacz element „Model Intrastat\Intrastat (Niemcy)”.


