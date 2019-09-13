---
title: Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych
description: W tym temacie wyjaśniono, w jaki sposób użytkownik przypisany do roli Administratora Systemu lub Programisty Elektronicznego Raportowania może utworzyć dostawcę konfiguracji dla Elektronicznego Raportowania (ER) w Dynamics 365 for Finance and Operations.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1d6df2068f99a42764fc13f282a7c38099109e06
ms.sourcegitcommit: f93ead945afe5ae18706c66bce6e64a6b57aac50
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/19/2019
ms.locfileid: "1887094"
---
# <a name="create-configuration-providers-and-mark-them-as-active"></a>Tworzenie dostawców konfiguracji i oznaczanie ich jako aktywnych

[!include [task guide banner](../../includes/task-guide-banner.md)]

W tym temacie wyjaśniono, w jaki sposób użytkownik przypisany do roli Administratora Systemu lub Programisty Elektronicznego Raportowania może utworzyć dostawcę konfiguracji dla Elektronicznego Raportowania (ER) w Dynamics 365 for Finance and Operations. Każda konfiguracja ER będzie się odnosiła do dostawcy jako autora konfiguracji. W tym przykładzie utworzysz dostawcę konfiguracji dla przykładowej firmy Litware, Inc. Podane kroki można wykonać w dowolnej firmie, ponieważ dostawcy konfiguracji ER są współużytkowani przez wszystkie firmy.

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
