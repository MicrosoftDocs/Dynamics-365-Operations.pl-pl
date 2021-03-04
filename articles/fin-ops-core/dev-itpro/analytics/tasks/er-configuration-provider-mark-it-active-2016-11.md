---
title: Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych
description: W tym temacie wyjaśniono, w jaki sposób użytkownik przypisany do roli Administratora Systemu lub Programisty Elektronicznego Raportowania może utworzyć dostawcę konfiguracji dla Elektronicznego Raportowania (ER).
author: NickSelin
manager: AnnBe
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7fb9f5be8571974237154ea704c93b8666c539a7
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4682004"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych

[!include [banner](../../includes/banner.md)]

W tym temacie wyjaśniono, w jaki sposób użytkownik przypisany do roli Administratora Systemu lub Programisty Elektronicznego Raportowania może utworzyć dostawcę konfiguracji dla Elektronicznego Raportowania (ER). Każda konfiguracja ER będzie się odnosiła do dostawcy jako autora konfiguracji. W tym przykładzie utworzysz dostawcę konfiguracji dla przykładowej firmy Litware, Inc. Podane kroki można wykonać w dowolnej firmie, ponieważ dostawcy konfiguracji ER są współużytkowani przez wszystkie firmy.

## <a name="create-a-provider"></a>Tworzenie dostawcy
1. Otwórz **okienko nawigacji** w górnym lewym rogu i wybierz **Administracja organizacji**.
2. Otwórz **Miejsca pracy > Electroniczne Raportowanie**.
3. Otwórz **Powiązane linki > Dostawcy konfiguracji**.
4. Wybierz pozycję **Nowy**.
    - Rekord dostawcy ma unikatową nazwę i adres URL. Przejrzyj zawartość tej strony i pomiń procedurę, jeśli rekord firmy Litware, Inc. (https://www.litware.com) już istnieje.  
5. W polu Nazwa wpisz `Litware, Inc.`.
6. W polu adres internetowy wpisz `https://www.litware.com`.
7. Wybierz opcję **Zapisz**.
8. Zamknij stronę.

## <a name="select-as-an-active-provider"></a>Ustawianie jako aktywnego dostawcy
1. Zaznacz dostawcę Litware, Inc.  
2. Wybierz **Aktywuj**.

![Strona obszaru roboczego raportowania elektronicznego](../media/GER-Task-ActiveProvider-1.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]