---
title: Zasady uprawnienia do świadczenia
description: Ten artykuł zawiera informacje o zasadach uprawnień do świadczeń, które pomagają określić, kto może otrzymywać określone świadczenia.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType, BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: a5046f1d32fb965c7cb3793daf1ba40b9c2a1d10
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5805905"
---
# <a name="benefit-eligibility-policies"></a>Zasady uprawnień do świadczeń

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ten artykuł zawiera informacje o zasadach uprawnień do świadczeń, które pomagają określić, kto może otrzymywać określone świadczenia.

Podczas tworzenia świadczeń określa się, które świadczenia będą dostępne dla których pracowników. W poniższej tabeli przedstawiono przykłady świadczeń, które można udostępnić określonym pracownikom.

| Świadczenie          | Dla kogo świadczenie jest dostępne |
|------------------|---------------------------------|
| Ubezpieczenie zdrowotne | Wszyscy pracownicy                   |
| Telefon komórkowy     | Pracownicy działu sprzedaży, kadra zarządzająca         |
| Przepustki parkingowe   | Kierownicy                      |

Następujące składniki są używane do tworzenia zasad uprawnień:

-   Typy reguł
-   Zasady uprawnienia do świadczenia

Typy reguł dla zasad definiują parametry kwerendy, które są używane podczas tworzenia określonych reguł dla zasad. Po utworzeniu typów reguł można utworzyć zasady uprawnień do świadczeń. Zasady pozwalają tworzyć zbiór reguł dotyczące jednego lub kilku podmiotów prawnych. W ramach każdej zasady można wyświetlić każdy z utworzonych wcześniej typów reguł dla zasad uprawnień do świadczenia. 

Użytkownik określa zakres reguły w obrębie zasady. Jeśli na przykład użytkownik utworzy typ reguły zasady uprawnienia do świadczenia o nazwie **Wykonawczy**, może określić, czym jest ta reguła w ramach zasady. W tym przykładzie reguła może stwierdzać, że powinna ona obejmować każde stanowisko ze słowem „wykonawczy” w nazwie. Po zdefiniowaniu parametrów reguły lub reguł, które są uwzględniane w zasadach, można przypisać regułę do świadczenia.






[!INCLUDE[footer-include](../includes/footer-banner.md)]