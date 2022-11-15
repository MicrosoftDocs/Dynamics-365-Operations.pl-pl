---
title: Wyliczenie wartości rozszerzalności bazowej rodzaju
description: Ten artykuł zawiera omówienie możliwości rozszerzania wyliczenia podstawy bazowe płci.
author: twheeloc
ms.date: 05/23/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: HRMParameters, EssWorkspace
audience: Application User
ms.custom:
- "51941"
- intro-internal
ms.assetid: 2cfb061a-a616-4bf9-9d98-9cde00039eec
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-03-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 61a80c16d24d8fda264340d79ed393db3f635908
ms.sourcegitcommit: 1717ff6af1879c6f3a8360936c42ecf55f86acd0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2022
ms.locfileid: "9749319"
---
# <a name="gender-base-enum-extensibility"></a>Wyliczenie wartości rozszerzalności bazowej rodzaju

Wyliczenie **Płeć** (wyliczenie) jest obecnie rozszerzalne. W tym artykule opisano zmiany, które należy wprowadzić w podstawie kodu, jeśli zamierzasz rozszerzyć wyliczenie różnicy między **Płciami**.

## <a name="gender-vs-hcmpersongender"></a>Rodzaj a HcmPersonGender

Istnieją dwa wyliczenia dla wartości rodzaju:

- **Płeć** (Platforma aplikacji)
- **HcmPersonGender** (PersonnelManagement)

Wyliczenie **Płeć** jest używane w całej usłudze Microsoft Dynamics 365 Finance, natomiast **HcmPersonGender** jest specyficzne dla funkcji zarządzania kapitałem ludzkim (HCM). Jeśli korzystasz z funkcji HCM i wprowadzasz zmiany w wyliczeniu **Płeć**, rozważ wprowadzenie tych samych zmian w wyliczeniu **HcmPersonGender**. Na przykład, jeśli dodasz **Transpłciowość** do wyliczenia **Płeć**, dodaj również **Transpłciowość** do wyliczenia **HcmPersonGender**.

## <a name="hcmpersongendertranformutil-class"></a>HcmPersonGenderTranformUtil (Class)

Utworzono nową klasę **HcmPersonGenderTranformUtil**, aby umożliwić tłumaczenie między dwoma modułami wyliczania podstawowego. W tej klasie istnieją dwie metody: **convertGenderToHcmPersonGender** i **convertHcmPersonGenderToGender**. Należy utworzyć rozszerzenie przy użyciu klasy **Łańcuch poleceń** lub **programów obsługi zdarzeń** i rozszerzyć obie metody, aby mapować nowe wartości, które są dodawane do wyliczenia podstawowego.

## <a name="payrollstatewagetaxprepdp-class"></a>PayrollStateWageTaxPrepDP (Class)

**PayrollStateWageTaxPrepDP** to klasa dostawcy danych dla raportu SSRS (**Payroll State Wage Tax Prep** SQL Server Reporting Services, SSRS). W Stanach Zjednoczonych dostępne są trzy wartości: **Męska**, **Damska** i **Nieokreślony**. W metodzie **populatePayrollStateWageTaxPrepTmp** znajduje się instrukcja switch służąca do odwzorowania wartości wyliczenia **HcmPersonGender** na jedno z trzech pól: **IsMale**, **IsFemale** lub **IsUnspecifiedGender**. Domyślną wartością instrukcji switch jest **IsUnspecifiedGender**. Jeśli dodasz jakiekolwiek wartości do wyliczenia **HcmPersonGender** w celu mapowania w inny sposób, musisz utworzyć rozszerzenie przy użyciu klasy **Łańcuch poleceń** w stosunku do metody **populatePayrollStateWageTaxPrepTmp**, aby zmienić wartość zgodnie z potrzebami .

## <a name="smmoutlooksync_contact-class"></a>smmOutlookSync_Contact (Class)

Klasa **smmOutlookSync_Contact** łączy wartości z programem **Outlook** i **osobami kontaktowymi**. **Program Outlook** obsługuje trzy wartości: **Męska**, **Damska** i **Nieokreślony**. Klasa ma dwie metody, które ułatwiają mapowanie **płci** na usługi **OutlookGenders**. Metodą domyślną jest **NonSpecific/UnSpecified**. Jeśli tworzysz dodatkowe wartości dla wyliczenia **Płeć**, powinieneś utworzyć rozszerzenie, używając klasy **Łańcuch poleceń** w stosunku do obu metod i odpowiednio mapować.
