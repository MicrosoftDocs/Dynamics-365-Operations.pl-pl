---
title: Uzyskiwanie dostępu do adresów prywatnych według ról zabezpieczeń
description: W tym temacie opisano, jak postępować, gdy odbiorca nie ma dostępu do prywatnych adresów.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0b96733946e4ef79de244730d0c442b9900426c1
ms.sourcegitcommit: 7e32e5e39e762a4b1606161cb603a450d13b5251
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/23/2021
ms.locfileid: "7413346"
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

![Strona parametrów globalnej książki adresowej.](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
