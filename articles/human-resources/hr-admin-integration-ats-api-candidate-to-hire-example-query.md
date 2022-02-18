---
title: Przykład kwerendy dotyczącej kandydata do zatrudnienia
description: Ten temat zawiera przykładowe zapytanie dotyczące jednostki Kandydata do zatrudnienia w Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: edb8687b9dae0afc1bc15a3a5c197e14e7e8cf1e
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/31/2022
ms.locfileid: "8069228"
---
# <a name="example-query-for-candidate-to-hire"></a>Przykład kwerendy dotyczącej kandydata do zatrudnienia


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Ten temat zawiera przykładowe zapytanie dotyczące jednostki Kandydata do zatrudnienia w Dynamics 365 Human Resources.

W tym temacie przedstawiono przykład demonstrujący, jak można używać *głębokich wstawień* do tworzenia wszystkich szczegółów nowego rekordu kandydata w jednej operacji interfejsu API. Aby uzyskać więcej informacji o operacjach głębokości, zobacz temat [Tworzenie powiązanych rekordów jednostek w jednej operacji](/powerapps/developer/data-platform/webapi/create-entity-web-api#create-related-entity-records-in-one-operation).

Jednostka **mshr_hcmcandidatetohireentity** jest unikatowa ze względu na jej relację z jednostką **mshr_dirpersonentity**. Wiele właściwości na tym **mshr_hcmcandidatetohireentity** (na przykład **mshr_firstname**, **mshr_lastname** i **mshr_birthdate**) pochodzi od rekordu **mshr_dirpersonentity**. Jeśli rekord nowego kandydata zostanie zaksięgowany bez **mshr_hcmcandidatetohireentity** wstawiania o głębokości, wartości tych właściwości można definiować bezpośrednio w rekordzie **mshr_hcmcandidatetohireentity**. Skojarzony **mshr_dirpersonentity** jest tworzony niejawnie przy użyciu zdefiniowanych wartości dla właściwości. Następnie możesz utworzyć inne powiązane rekordy encji (takie jak umiejętności lub wykształcenie) jako oddzielne wywołania interfejsu API.

Jeśli jednak chcesz użyć głębokiego wstawiania do tworzenia wszystkich powiązanych jednostek w jednej operacji, właściwości specyficzne dla jednostki **mshr_dirpersonentity** muszą być zdefiniowane na tym zagnieżdżonym poziomie operacji.

Ten przykład pokazuje, jak można utworzyć rekord kandydata, powiązany rekord osoby oraz umiejętności i wykształcenie osoby na trzech zagnieżdżonych poziomach przy użyciu głębokiego wstawiania w jednej operacji interfejsu API.

> [!NOTE]
> W tym przykładzie nie są dołączane wszystkie właściwości poszczególnych jednostek API. Jest uproszczony w celach demonstracyjnych.

**Wniosek**

```http

POST [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities
Content-Type: application/json; charset=utf-8
OData-MaxVersion: 4.0
OData-Version: 4.0
Accept: application/json

{
    "mshr_dataareaid": "usmf",
    "mshr_recruitingrequestid": "USMF-000141",
    "mshr_positionid": "000601",
    "mshr_iswillingtorelocate": 200000000,
    "mshr_availabilitydate": "2021-03-18",
    "mshr_comments": "Evelyn's experience is exactly what we need for this position.",
    "mshr_FK_Person_id":
        {
            "mshr_firstname": "Evelyn",
            "mshr_lastname": "Chambers",
            "mshr_namesequencedisplayas": "FirstMiddleLast",
            "mshr_FK_HcmPersonSkillEntity_Person":
            [
                {
                    "mshr_skillid": "CustFocus",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                },
                {
                    "mshr_skillid": "CashFlow",
                    "mshr_ratingid": "Skills",
                    "mshr_levelid": "4",
                    "mshr_ratinglevelexaminer": "",
                    "mshr_leveltype": 200000000,
                    "mshr_yearsofexperience": 0,
                    "mshr_verified": 200000000,
                    "mshr_leveldate": "2013-01-01T00:00:00Z"
                }
            ],
            "mshr_FK_HcmPersonEducationEntity_Person": [
                {
                    "mshr_creditbasis": 200000000,
                    "mshr_enddate": "2021-02-22T00:00:00Z",
                    "mshr_educationlevelid": "Bachelor",
                    "mshr_creditsearned": 0,
                    "mshr_startdate": "2017-02-21T00:00:00Z",
                    "mshr_creditscompleted": 0,
                    "mshr_educationinstitutionid": "Cottonwood Univ",
                    "mshr_educationdisciplineid": "Business Mgmt",
                    "mshr_durationunit": 200000000
                }              
            ]
        }
}
```

**Odpowiedź**

```http

HTTP/1/1 204 No Content
OData-Version: 4.0
OData-EntityId: [Organization URI]/api/data/v9.1/mshr_hcmcandidatetohireentities(00000d2d-0000-0000-7317-005001000000)

```

## <a name="see-also"></a>Informacje dodatkowe

[Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów](hr-admin-integration-ats-api-introduction.md)<br>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
