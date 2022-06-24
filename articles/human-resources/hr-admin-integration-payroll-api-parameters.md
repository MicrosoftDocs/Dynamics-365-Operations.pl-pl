---
title: Parametry integracji płac
description: W tym artykule opisano parametry integracji Listy płac w aplikacji Dynamics 365 Human Resources.
author: marcelbf
ms.date: 06/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-17
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7d784909fc8c5fa05557566b62b19802cd2acece
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896113"
---
# <a name="payroll-integration-parameters"></a>Parametry integracji płac


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Przed użyciem integracji listy płac w aplikacji Dynamics 365 Human Resources musisz skonfigurować parametry opisane w tym artykule.

## <a name="enable-payroll-address"></a>Włącz adres listy płac

Aby móc korzystać z adresu listy płac, należy go włączyć w [formularzu parametrów współdzielonych](hr-setup-shared-parameters.md) na karcie Integracja listy płac.

## <a name="define-the-identification-type"></a>Określ typ identyfikacji

Aby ujawnić identyfikator typu identyfikacji w [encji pracownika listy płac](hr-admin-integration-payroll-api-payroll-employee.md), należy  [skonfigurować parametry zasobów ludzkich dla każdej firmy](hr-setup-shared-parameters.md).

1. W obszarze roboczym **Zarządzanie kompensacją** w sekcji łącza wybierz opcję **Parametry Human Resources**. 
2. Na karcie **Integracja listy płac** określ wartości w następujących polach.

| Pole | opis |
| --- | --- |
| Użyj typów identyfikacji w przetwarzaniu listy płac | Gdy ta opcja jest zaznaczona, wybrany identyfikator typu zostanie ujawniony w encji pracownik listy płac. |
| Typ identyfikacji | Typ identyfikacji do udostępnianej w polu **mshr_payrollemployeeentityid** [jednostka pracownik listy płac](hr-admin-integration-payroll-api-payroll-employee.md). |

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do API integracji płac](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
