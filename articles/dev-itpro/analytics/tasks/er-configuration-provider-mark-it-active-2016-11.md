--- 
title: Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego na potrzeby raportowania elektronicznego (ER)
description: "W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć dostawcę konfiguracji dla raportowania elektronicznego (ER)."
author: NickSelin
manager: AnnBe
ms.date: 11/01/2017
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
ms.sourcegitcommit: 809a1466b0f4674f503bc654175d8f94b37a6508
ms.openlocfilehash: 2dfa04f280249884af2a237807fb283059444a6c
ms.contentlocale: pl-pl
ms.lasthandoff: 11/02/2017

---
# <a name="create-a-configuration-provider-and-mark-it-as-active-for-electronic-reporting-er"></a>Tworzenie dostawcy konfiguracji i oznaczanie go jako aktywnego na potrzeby raportowania elektronicznego (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć dostawcę konfiguracji dla raportowania elektronicznego (ER). Każda konfiguracja ER będzie się odnosiła do dostawcy jako autora konfiguracji. W tym przykładzie utworzysz dostawcę konfiguracji dla przykładowej firmy Litware, Inc. Podane kroki można wykonać w dowolnej firmie, ponieważ dostawcy konfiguracji ER są współużytkowani przez wszystkie firmy.


## <a name="create-a-provider"></a>Tworzenie dostawcy
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Kliknij opcję Dostawcy konfiguracji.
3. Kliknij przycisk Nowy.
    * Rekord dostawcy ma unikatową nazwę i adres URL. Przejrzyj zawartość tej strony i pomiń procedurę, jeśli rekord firmy Litware, Inc. (http://www.litware.com) już istnieje.  
4. W polu Nazwa wpisz „Litware, Inc.”.
    * Litware, Inc.  
5. W polu Adres internetowy wpisz „http://www.litware.com”.
    * http://www.litware.com  
6. Kliknij przycisk Zapisz.
7. Zamknij stronę.

## <a name="select-as-an-active-provider"></a>Ustawianie jako aktywnego dostawcy
1. Zaznacz dostawcę Litware, Inc.  
2. Kliknij opcję Ustaw jako aktywny.


