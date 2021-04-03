---
title: MyLeaveRequests — omówienie
description: Jednostka MyLeaveRequests w programie Microsoft Dynamics 365 Human Resources udostępnia listę wniosków urlopowych w systemie, ograniczoną do wniosków dostępnych dla bieżącego użytkownika wykonującego zapytanie o jednostkę.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: c2c14a0cc935ad166a2c6600f1e96c3e09ab16ca
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465517"
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