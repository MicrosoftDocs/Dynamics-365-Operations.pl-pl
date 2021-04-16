---
title: MyLeaveRequests — omówienie
description: Jednostka MyLeaveRequests w programie Microsoft Dynamics 365 Human Resources udostępnia listę wniosków urlopowych w systemie, ograniczoną do wniosków dostępnych dla bieżącego użytkownika wykonującego zapytanie o jednostkę.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 44e23a076733bac782a0366aeba3456911522abe
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803640"
---
# <a name="myleaverequests-overview"></a>MyLeaveRequests — omówienie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Jednostka MyLeaveRequests w programie Microsoft Dynamics 365 Human Resources udostępnia listę wniosków urlopowych w systemie, ograniczoną do wniosków dostępnych dla bieżącego użytkownika wykonującego zapytanie o jednostkę.

## <a name="key"></a>Klucz

  | Nazwa właściwości | Typ danych |
  |---------------|-----------|
  | dataAreaId    | Ciąg    |
  | RequestId     | Ciąg    |
  | LeaveType     | Ciąg    |
  | LeaveDate     | Data      |
  
## <a name="properties"></a>Właściwości

  | Nazwa właściwości     | Typ danych | Potrzebne |
  |-------------------|-----------|----------|
  | dataAreaId        | Ciąg    | X        |
  | RequestId         | Ciąg    | X        |
  | LeaveType         | Ciąg    | X        |
  | LeaveDate         | Data      | X        |
  | ReasonCodeId      | Ciąg    |          |
  | PersonnelNumber   | Ciąg    | X        |
  | RequestDate       | Data      | X        |
  | Komentarz           | Ciąg    |          |
  | Stan            | Wyliczenie      | X        |
  | Liczba dni            | Rzeczywisty      |          |
  | HalfDayDefinition | Wyliczenie      |          |

## <a name="actions"></a>Akcje

 | Nazwa akcji                               | Opis                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [przesyłanie](hr-developer-api-myleaverequests-submit.md)   | Przesyłanie wniosku do przetworzenia w przepływie pracy. |

## <a name="see-also"></a>Informacje dodatkowe

- [Przesyłanie wniosku o urlop do przepływu pracy](hr-developer-api-myleaverequests-submit.md)
- [Uwierzytelnianie](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]