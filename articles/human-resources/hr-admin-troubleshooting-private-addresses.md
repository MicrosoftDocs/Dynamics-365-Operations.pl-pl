---
title: Uzyskiwanie dostępu do adresów prywatnych według ról zabezpieczeń
description: W tym artykule opisano, jak rozwiązać problem, gdy odbiorca nie ma dostępu do prywatnych adresów.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
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
ms.openlocfilehash: 6598094e7877a30c35e1b03794f82c8a4ec001a7
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113825"
---
# <a name="access-to-private-addresses-by-security-role"></a>Uzyskiwanie dostępu do adresów prywatnych według ról zabezpieczeń

**Wydaj**

Po odbiorca zduplikuje rolę zabezpieczeń zaloguje się jako nowa rola, nie widzi adresów oznaczonych jako prywatne.

**Rozdzielczość**

Aby rozwiązać ten problem, odbiorca musi wykonać następujące kroki dla zduplikowanej roli zabezpieczeń.

1. Wybierz kolejno opcje **Administrowanie organizacją \> Globalna książka adresowa \> Parametry globalnej książki adresowej**.
2. Na karcie **zabezpieczenia lokalizacji prywatnych** przenieś nową rolę zabezpieczeń z listy **dostępnych ról** na listę **wybrane role**.
3. Wybierz opcję **Zapisz**.

![Strona parametrów globalnej książki adresowej](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]