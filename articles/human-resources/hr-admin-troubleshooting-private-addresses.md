---
title: Uzyskiwanie dostępu do adresów prywatnych według ról zabezpieczeń
description: W tym artykule opisano, jak rozwiązać problem, gdy odbiorca nie ma dostępu do prywatnych adresów.
author: andreabichsel
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8daee1b645836e96a4bf3057cb317d5409d4583a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803928"
---
# <a name="access-to-private-addresses-by-security-role"></a>Uzyskiwanie dostępu do adresów prywatnych według ról zabezpieczeń

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Wydaj**

Po odbiorca zduplikuje rolę zabezpieczeń zaloguje się jako nowa rola, nie widzi adresów oznaczonych jako prywatne.

**Rozdzielczość**

Aby rozwiązać ten problem, odbiorca musi wykonać następujące kroki dla zduplikowanej roli zabezpieczeń.

1. Wybierz kolejno opcje **Administrowanie organizacją \> Globalna książka adresowa \> Parametry globalnej książki adresowej**.
2. Na karcie **zabezpieczenia lokalizacji prywatnych** przenieś nową rolę zabezpieczeń z listy **dostępnych ról** na listę **wybrane role**.
3. Wybierz opcję **Zapisz**.

![Strona parametrów globalnej książki adresowej](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]