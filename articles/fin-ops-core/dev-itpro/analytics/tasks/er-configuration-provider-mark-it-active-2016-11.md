---
title: Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych
description: W tym temacie wyjaśniono, w jaki sposób użytkownik przypisany do roli Administratora systemu lub Dewelopera raportowania elektronicznego może utworzyć dostawcę konfiguracji.
author: NickSelin
ms.date: 07/02/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERVendorTable
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9428ff1f53928f104df4736911ce34756128da44
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6359442"
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

![Strona obszaru roboczego raportowania elektronicznego.](../media/GER-Task-ActiveProvider-1.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]