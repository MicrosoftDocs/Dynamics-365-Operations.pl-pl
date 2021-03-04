---
title: Śledzenie zmian w danych dotyczących rekrutacji
description: Funkcja inspekcji procesów umożliwia śledzenie informacji o kandydatach, otwartych zadaniach lub zmianach zgłoszeń o pracę z przyczyn związanych z raportowaniem lub zgodnością.
author: tracykeya
manager: AnnBe
ms.date: 04/17/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application user
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-04-30
ms.dyn365.ops.version: AX 7.1.0, Talent April 2019 update
ms.openlocfilehash: c009f82e69bff0e4ea540514de8f9e60eca1e466
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462275"
---
# <a name="track-changes-in-recruiting-data"></a>Śledzenie zmian w danych dotyczących rekrutacji

[!include [banner](includes/banner.md)]

Można śledzić zmiany wprowadzone do kandydatów, otwartych zadań lub zgłoszeń o pracę, korzystając z funkcji przetwarzania inspekcji. Jest to przydatne w przypadku raportowania i zgodności.

Można wyświetlić śledzone dane w Power BI za pomocą łącznika OData. Aby uzyskać więcej informacji, zobacz [łączenie ze źródłami danych OData w systemie Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-connect-odata).

## <a name="track-changes"></a>Śledzenie zmian
Aby skonfigurować śledzenie zmian w danych dotyczących rekrutacji, wykonaj następujące kroki:

1. W [Power Apps](https://web.powerapps.com), wybierz odpowiednie środowisko.

2. Wybierz **ustawienia** (ikona koła zębatego), wybierz opcję **zaawansowane dostosowania**, a następnie wybierz **zasoby** wobszarze **zasoby deweloperów**. 

3. Na stronie **zasoby deweloperów** skopiuj wartość w polu **wartość interfejsu API Web**. Na przykład wartość może wyglądać następująco: https://yourorgname.api.crm.dynamics.com/api/data/v9.1/.

4. Następnie można wykonać kwerendę dotyczącą danych z jednej z następujących jednostek:
  - Historia otwierania zadań (msdyn_jobopeninghistories)
  - Historia zgłoszeń o pracę (msdyn_jobapplicationhistories) 
  - Historia kandydatów (msdyn_candidatehistories)

## <a name="data-reported"></a>Zgłoszone dane

W procesie inspekcji są dostępne następujące dane:

| Zgłoszone dane | Opis |
| --- | --- |
| Zmienione przez (msdyn_ChangedbyId) | Odwołanie do użytkownika |
| Utworzono w dniu |  Data i godzina w formacie UTC, gdy nastąpiła zmiana |
| Typ zmiany (msdyn_changetype) | Jak doszło do zmiany |
| Wspólne wartości dla kandydatów, wakatów, <br></br>zgłoszeń o pracę | Utworzono<br></br>Zaktualizowano |
| Historia zgłoszeń o pracę | Dodane artefakty <br></br>Usunięte artefakty |
| Historia wakatu | Do zrobienia: post dodany <br></br>Do zrobienia: post usunięty <br></br>Do zrobienia: post zaktualizowany <br></br>Do zrobienia: dodano uczestnika <br></br>Do zrobienia: uczestnik usunięty |
| Historia kandydata | Dodane artefakty <br></br>Usunięte artefakty <br></br>Doświadczenie zawodowe dodane <br></br>Doświadczenie zawodowe usunięte <br></br>Wykształcenie dodane <br></br>Wykształcenie usunięte <br></br>Kwalifikacja dodana <br></br>Kwalifikacja usunięta <br></br>Dodano znacznik <br></br>Usunięto znacznik <br></br>Sieci społecznościowe dodane <br></br>Sieci społecznościowe usunięte <br></br>Dane osobowe dodane <br></br>Dane osobowe zaktualizowane<br></br> |
| Zmienione pola (msdyn_changedfields) | Obiekt JSON z listą zmienionych pól może nie przechowywać wartości dla wszystkich pól.<br></br><br></br>W przypadku zmian „utworzonych” i „zaktualizowanych” zostaną pokazane pola w utworzonym lub zmodyfikowanym rekordzie.<br></br><br></br>W przypadku zmian typu „dodane” zostaną wystawione pola w rekordzie podrzędnym.<br></br><br></br>**Przykład:**<br></br><br></br>{<br></br>  "msdyn_applyurl": { "newValue": "" },<br></br>  "msdyn_description": { "valueOmitted": true } <br></br>} |
|Historia zgłoszeń o pracę | Zgłoszenie o pracę (msdyn_JobapplicatonId)<br></br>Stan (msdyn_status) <br></br>Przyczyna stanu (msdyn_statusreason) <br></br>Przyczyna odrzucenia (msdyn_rejectionreason) |
| Historia wakatu | Wakat (msdyn_JobopeningId) <br></br>Stan (msdyn_jobopeningstatus) <br></br>Przyczyna stanu (msdyn_jobopeningstatusreason) |
| Historia kandydata | Kandydat (msdyn_CandidateId) |


[!INCLUDE[footer-include](../includes/footer-banner.md)]