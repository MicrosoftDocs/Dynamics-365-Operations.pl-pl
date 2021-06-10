---
title: Uzyskiwanie dostępu do adresów prywatnych według ról zabezpieczeń
description: W tym artykule opisano, jak rozwiązać problem, gdy odbiorca nie ma dostępu do prywatnych adresów.
author: andreabichsel
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2edcef338f0ff8fcf231d4314fc972284397d000
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053330"
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