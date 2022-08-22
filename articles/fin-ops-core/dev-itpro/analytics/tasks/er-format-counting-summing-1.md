---
title: ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 1 — Tworzenie formatu)
description: W tym artykule opisano sposób konfigurowania formatu raportowania elektronicznego do zliczania i sumowania na podstawie danych już wygenerowanego tekstu wyjściowego. (część 1)
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form:
- ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport
- ERSolutionTable
ms.openlocfilehash: b9e0128e55ba6ab356d6942020a34e5e74d6b7e2
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290703"
---
# <a name="er-configure-format-to-do-counting-and-summing-part-1---create-format"></a>ER Konfigurowanie formatu do inwentaryzacji i sumowania (Część 1 — Tworzenie formatu)

[!include [banner](../../includes/banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli administratora systemu lub dewelopera raportowania elektronicznego może tak skonfigurować format raportowania elektronicznego (ER), aby wykonywał inwentaryzację i sumowanie na podstawie danych już wygenerowanych tekstów wyjściowych. Kroki można wykonać na danych dowolnej firmy.

Aby wykonać te kroki, należy najpierw wykonać kroki w procedurze „Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego”.

Procedura dotyczy funkcji dodanej w programie Dynamics 365 for Operations w wersji 1611.


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Uzyskiwanie dostępu do listy konfiguracji dostarczanej przez firmę Microsoft
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
    * Upewnij się, że dostawca „Litware, Inc.” jest dostępny i oznaczony jako aktywny.  
2. Wybierz dostawcę „Litware, Inc.”.  
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



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
