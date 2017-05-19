---
title: "Zasady uprawnienia do świadczenia"
description: "Ten artykuł zawiera informacje o zasadach uprawnień do świadczeń, które pomagają określić, kto może otrzymywać określone świadczenia."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HcmBenefitEligibilityDetail, SysPolicyListPage, SysPolicySourceDocumentRuleType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16441
ms.assetid: 4ad0106f-5b07-4fd5-bc1a-5834fa9b198e
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 076b4f14a09698b6a0e2f5f3dd4f74ef5b673a8d
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="benefit-eligibility-policies"></a>Zasady uprawnienia do świadczenia

[!include[banner](includes/banner.md)]


Ten temat zawiera informacje o zasadach uprawnień do świadczeń, które pomagają określić, kto może otrzymywać określone świadczenia.

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

<a name="see-also"></a>Informacje dodatkowe
--------

[Definiowanie programu świadczeń i zarządzanie nim](manage-benefit-program.md)




