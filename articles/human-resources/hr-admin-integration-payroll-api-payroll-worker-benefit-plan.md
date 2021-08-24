---
title: Plan świadczeń pracowników listy płac
description: Ten temat zawiera szczegółowe informacje i przykładowe zapytanie dotyczące relacji jednostki korzyści pracownicze plany wynagrodzeń w Dynamics 365 Human Resources.
author: marcelbf
ms.date: 07/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0837d9a153aba554d0a5293d16afb309bd37963c270da5b67e691558cae63b0a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6758719"
---
# <a name="payroll-worker-benefit-plan"></a>Plan świadczeń pracowników listy płac

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano encję plan korzyści stałych dla Dynamics 365 Human Resources.

Nazwa fizyczna: mshr_payrollworkerbenefitplanentities.

### <a name="description"></a>opis

Ta encja dostarcza informacji o planie świadczeń dla danego pracownika.

## <a name="properties"></a>Właściwości

| Właściwość</br>**Nazwa fizyczna**</br>**_Typ_** | Użycie | opis |
| --- | --- | --- |
| **Numer pracownika**</br>mshr_personnelnumber</br>*Ciąg* | Tylko do odczytu</br>Potrzebne | Unikalny numer personelu pracownika. |
| **Identyfikator firmy**</br>mshr_legalentityID</br>*Ciąg* | Tylko do odczytu | Określa osobę prawną (firmę). |
| **Identyfikator okresu**</br>mshr_periodid</br>*Ciąg* | Tylko do odczytu | Identyfikator okresu. |
| **Identyfikator planu**</br>mshr_planid</br>*Ciąg* | Tylko do odczytu | Identyfikator planu. |
| **Opcja objęcia świadczeniem**</br>mshr_coverageoptionid</br>*Ciąg* | Tylko do odczytu | Identyfikacja opcji zapotrzebowania. |
| **Data rozpoczęcia potrącenia**</br>mshr_deductionstartdatetime</br>*Przesunięcie daty i godziny* | Tylko do odczytu | Data rozpoczęcia potrącenia. |
| **Data zakończenia potrącenia**</br>mshr_deductionenddatetime</br>*Przesunięcie daty i godziny* | Tylko do odczytu | Data zakończenia potrącenia. |
| **Stan**</br>mshr_status</br>*[Status zestawu opcji planu pracownika etatowego świadczeń](hr-admin-integration-payroll-api-benefit-employee-plan-status.md)* | Tylko do odczytu | Status dla programu świadczeń. |
| **Data wejścia w życie**</br>mshr_validfrom</br>*Przesunięcie daty i godziny* | Tylko do odczytu | Godzina rozpoczęcia ważności tego rekordu. |
| **Data ważności**</br>mshr_validto</br>*Przesunięcie daty i godziny* |  Tylko do odczytu | Godzina zakończenia ważności tego rekordu. |
| **Identyfikator typu planu**</br>mshr_plantypeid</br>*Ciąg* | Tylko do odczytu | Identyfikator typu planu. |
| **Kod typu planu**</br>mshr_plantypecode</br>*[Zestaw opcji typu planu świadczeń](hr-admin-integration-payroll-api-benefit-plan-type-cover.md)* | Tylko do odczytu | Specyfikacja typu planu. |
| **Liczba okresów płac**</br>mshr_payperiod</br>*Wartość całkowita* | Tylko do odczytu | Liczba okresów płacowych reprezentująca częstotliwość płacenia dostawcom świadczeń lub pracownikom. Ta kwota będzie używana do obliczania kwoty rocznego wynagrodzenia z tytułu świadczenie dla pracownika. |
| **Kwota pracownika etatowego**</br>mshr_amountemployee</br>*Dziesiętny* | Tylko do odczytu | Kwota lub procent pracownika. |
| **Kwota pracodawcy**</br>mshr_amountemployer</br>*Dziesiętny* | Tylko do odczytu | Kwota lub procent pracodawcy. |
| **Pole główne**</br>mshr_primaryfield</br>*Ciąg* | Wygenerowany przez system | Pole główne. |
| **Wartość identyfikatora pracownika** </br>_mshr_fk_worker_id_value</br>*GUID* | Klucz obcy: mshr_hcmworkerbaseentityid jednostki mshr_hcmworkerbaseentity. | Wygenerowany przez system unikatowy identyfikator pracownika. |
| **Wartość identyfikatora okresu**</br> _mshr_fk_period_id_value</br>*GUID* | Klucz obcy: mshr_benefitperiodentityid encji mshr_benefitperiodentity. | Wygenerowany przez system unikatowy identyfikator okresu. |
| **Wartość identyfikatora planu**</br> _mshr_fk_plan_id_value</br>*GUID* | Klucz obcy: mshr_benefitplanentityid z encji mshr_benefitplanentity | Wygenerowany przez system unikatowy identyfikator planu. |
| **Wartość identyfikacyjna typu planu**</br> _mshr_fk_plantype_id_value</br>*GUID* | Klucz obcy: mshr_benefitplantypeentityid z encji mshr_benefitplantypeentity. | Wygenerowany przez system unikatowy identyfikator planu. |
| **Wartość identyfikatora opcji zapotrzebowania**</br> _mshr_fk_coverageoption_id_value</br>*GUID* | Klucz obcy: mshr_benefitcoverageoptionentityid encji mshr_benefitcoverageoptionentity. | Wygenerowany przez system unikatowy identyfikator planu. |
| **Wartość identyfikacyjna podmiotu programu świadczeń pracowniczych na liście płac**</br> mshr_payrollworkerbenefitplanentityid</br>*GUID* | Tylko do odczytu </br> Wygenerowany przez system | Wygenerowany przez system unikatowy identyfikator rekordu. |

## <a name="example-query-for-payroll-worker-benefit-plan"></a>Przykładowa kwerenda dla planu świadczeń pracownika listy płac

**Wniosek**

```http
GET [Organization URI]/api/data/v9.1/mshr_payrollworkerbenefitplanentities?$filter=mshr_personnelnumber eq '000020'
```

**Odpowiedź**

```json
{
    "mshr_personnelnumber": "000020",
    "mshr_legalentityid": "USMF",
    "mshr_periodid": "2021",
    "mshr_planid": "Dental plan",
    "mshr_coverageoptionid": "Emp Only",
    "mshr_deductionstartdatetime": "2021-01-01T06:00:00Z",
    "mshr_deductionenddatetime": "2021-12-31T06:00:00Z",
    "mshr_status": 200000001,
    "mshr_validfrom": "2021-01-01T06:00:00Z",
    "mshr_validto": "2021-12-31T06:00:00Z",
    "mshr_plantypeid": "Dental",
    "mshr_plantypecode": 200000001,
    "mshr_payperiod": 12,
    "mshr_amountemployee": 47,
    "mshr_amountemployer": 57,
    "mshr_primaryfield": "000020 | USMF | 2021 | Dental plan",
    "_mshr_fk_worker_id_value": "000000ae-0000-0000-bfff-004105000000",
    "_mshr_fk_period_id_value": "00000807-0000-0000-ee02-005001000000",
    "_mshr_fk_plan_id_value": "00000c61-0000-0000-0200-005001000000",
    "_mshr_fk_plantype_id_value": "0000057c-0000-0000-0200-005001000000",
    "_mshr_fk_coverageoption_id_value": "00000391-0000-0000-0b00-005001000000",
    "mshr_payrollworkerbenefitplanentityid": "000006c4-0000-0000-bfff-004105000000"
}
```
## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do API integracji płac](hr-admin-integration-payroll-api-introduction.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
