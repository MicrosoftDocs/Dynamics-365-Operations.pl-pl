--- 
title: "Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych"
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
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 37957f224cb57fd9f6c5014740bcea124a99a03a
ms.contentlocale: pl-pl
ms.lasthandoff: 08/09/2018

---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych

[!include [task guide banner](../../includes/task-guide-banner.md)]

W poniższych krokach wyjaśniono, jak użytkownik przypisany do roli Administrator systemu lub Deweloper raportowania elektronicznego może utworzyć dostawcę konfiguracji dla raportowania elektronicznego (ER). Każda konfiguracja ER będzie się odnosiła do dostawcy jako autora konfiguracji. W tym przykładzie utworzysz dostawcę konfiguracji dla przykładowej firmy Litware, Inc. Podane kroki można wykonać w dowolnej firmie, ponieważ dostawcy konfiguracji ER są współużytkowani przez wszystkie firmy.


## <a name="create-a-provider"></a>Tworzenie dostawcy
1. Wybierz kolejno opcje Administrowanie organizacją > Obszary robocze > Raportowanie elektroniczne.
2. Kliknij opcję Dostawcy konfiguracji.
3. Kliknij przycisk Nowy.
    * Rekord dostawcy ma unikatową nazwę i adres URL. Przejrzyj zawartość tej strony i pomiń procedurę, jeśli rekord firmy Litware, Inc. (`http://www.litware.com`) już istnieje.  
4. W polu Nazwa wpisz „Litware, Inc.”.
    * Litware, Inc.  
5. W polu Adres internetowy wpisz wartość `http://www.litware.com`.
6. Kliknij przycisk Zapisz.
7. Zamknij stronę.

## <a name="select-as-an-active-provider"></a>Ustawianie jako aktywnego dostawcy
1. Zaznacz dostawcę Litware, Inc.  
2. Kliknij opcję Ustaw jako aktywny.


