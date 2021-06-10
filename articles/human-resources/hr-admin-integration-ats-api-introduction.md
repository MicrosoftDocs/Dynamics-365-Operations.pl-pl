---
title: Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów
description: W tym temacie opisano interfejs API integracji systemu śledzenia kandydatów (ATS) Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 02/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c043ac9c19a810d1718f0d4907cd5e9d651d778f
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6055299"
---
# <a name="applicant-tracking-system-integration-api-introduction"></a>Wprowadzenie do interfejsu API integracji systemu śledzenia kandydatów

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym temacie opisano interfejs API integracji systemu śledzenia kandydatów (ATS) Dynamics 365 Human Resources. Celem API jest umożliwienie usprawnionej integracji między Dynamics 365 Human Resources i współpracującymi ATS.

![Przepływ integracji ATS](media/hr-admin-integration-ats-api-introduction-flow.png)

Zintegrowane doświadczenie zaczyna się w dziale zasobów ludzkich, gdy kierownik kadr tworzy wniosek rekrutacyjny. Gdy wniosek zostanie uaktywniony, ATS ściąga szczegóły wniosku o utworzenie projektu rekrutacji. Następnie następuje rekrutacja, aby wybrać i zatrudnić kandydata na dane stanowisko. Na koniec ATS kończy integrację w obie strony, przesyłając rekord wybranego kandydata do działu kadr. Rekord kandydata może następnie przejść przez kolejne walidacje wprowadzające i przepływy pracy, aby utworzyć rekord pracownika.

Aby włączyć integrację, w składniku Human Resources zostały dodane następujące składniki:

1.  Funkcja do tworzenia wniosku o rekrutację.
2.  Rozwinięty profil kandydata i powiązane przepływy pracy.
3.  Integracyjny interfejs API, otwierający nową funkcjonalność do integracji aplikacji.

Aby uzyskać więcej informacji na temat konfigurowania i korzystania z prośby o rekrutację i funkcji kandydata, zobacz [Rekrutowanie kandydatów do pracy](hr-personnel-recruit.md).

## <a name="microsoft-dataverse"></a>Microsoft Dataverse

Ten interfejs API jest wbudowany Microsoft Dataverse (poprzednio Common Data Service). Cała interakcja RESTful z tym interfejsem API odbywa się za pośrednictwem internetowego interfejsu API Microsoft Dataverse, który korzysta z protokołu OData. Ten interfejs API jest podzestawem interfejsu API sieci Web Dataverse. Interfejs API sieci Web Dataverse definiuje cechy, takie jak uwierzytelnianie, umowy SLA, partia, kontrola współbieżności i obsługa błędów.

Aby uzyskać więcej ogólnych informacji na temat interfejsu API sieci Web Microsoft Dataverse, zobacz:

- [Co to jest usługa Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)
- [Użyj interfejsu API sieci Web Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)
- [Podręcznik dewelopera Microsoft Dataverse](/powerapps/developer/data-platform)

Powyższe dokumentacja zawiera szczegółowe wskazówki dla programistów dotyczące używania interfejsu API sieci Web Dataverse, takie jak [zarządzanie uwierzytelnianiem](/powerapps/developer/data-platform/webapi/authenticate-web-api), [wykonywanie operacji](/powerapps/developer/data-platform/webapi/perform-operations-web-api), [używanie Postmana z interfejsem API](/powerapps/developer/data-platform/webapi/use-postman-web-api) oraz [korzystanie z tokenów śledzenia zmian lub różnic](/powerapps/developer/data-platform/use-change-tracking-synchronize-data-external-systems) z interfejsem API.

### <a name="option-sets"></a>Zestawy opcji

Model danych dla interfejsu API integracji ATS opisany w tym dokumencie obejmuje zestawy opcji, które zapewniają wyliczone wartości powiązane z właściwościami jednostki. Aby uzyskać szczegółowe informacje dotyczące pracy z zestawami opcji w interfejsie API sieci Web Dataverse, zobacz temat [Tworzenie i aktualizowanie zestawów opcji przy użyciu interfejsu API sieci Web](/powerapps/developer/data-platform/webapi/create-update-optionsets). Zestawy opcji są definiowane dla każdego środowiska Dataverse.

### <a name="virtual-tables-for-human-resources-in-dataverse"></a>Wirtualne tabele dla Human Resources w Dataverse

Punkty końcowe dla interfejsu API integracji ATS korzystają z możliwości platformy tabel wirtualnych Microsoft Dataverse. Domyślnie tabele wirtualne i skojarzone z nimi punkty końcowe interfejsu API nie są wdrażane w środowiskach Human Resources, co umożliwia organizacjom określenie, które punkty końcowe OData będą widoczne dla środowiska. Aby można było korzystać z interfejsu API, należy wygenerować tabele wirtualne dla jednostek Human Resources dla środowiska. 

Aby uzyskać informacje dotyczące generowania tabel wirtualnych dla interfejsu API, zobacz temat [Konfigurowanie tabel wirtualnych Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="data-model"></a>Model danych

Model danych jest na środku dwóch głównych jednostek:

- **RecruitingRequest** reprezentuje żądanie skierowane do ATS w celu rekrutacji na jedno lub więcej wolnych stanowisk. Aby zapoznać się z przykładowym zapytaniem, zobacz [Przykładowe zapytanie dotyczące wniosku rekrutacyjnego](hr-admin-integration-ats-api-recruiting-request-example-query.md).
- **CandidateToHire** przedstawia szczegóły kandydata, który zaakceptował ofertę na stanowisko. **Osoba** reprezentuje osobę, która jest kandydatem. Osoba może pełnić w firmie wiele ról, takich jak kandydat, pracownik, pracownik pełnoetatowy czy zleceniobiorca. Aby uzyskać przykładowe zapytanie, zobacz [Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md).

Poniższy diagram ilustruje relacje w ramach interfejsu API. Kilka typów ma klucze obce do innych, wcześniej istniejących jednostek w dziale Human Resources, które nie zostały tutaj zilustrowane. Ten dokument zawiera informacje o jednostkach, które są specyficzne dla scenariuszy integracji rekrutacji. W interfejsie API sieci Web Dataverse istnieje jednak wiele innych jednostek, które mogą być także istotne dla integracji Dynamics 365 Human Resources. Na przykład mogą być potrzebne szczegółowe informacje dotyczące pracowników, stanowisk, stanowisk lub innych jednostek, które nie zostały tutaj zdefiniowane. Wiele z tych jednostek odwołuje się do relacji klucza obcego lub właściwości nawigacji.

![Model danych ATS integracji API](media/hr-admin-integration-ats-api-data-model.png)

## <a name="recruiting-request-and-related-entities-and-option-sets"></a>Żądania rekrutacji oraz powiązane jednostki i zestawy opcji

Przykład kwerendy: 

- [Przykładowa kwerenda dla wniosku o rekrutację](hr-admin-integration-ats-api-recruiting-request-example-query.md)

Jednostki:

- [Wniosek o rekrutację](hr-admin-integration-ats-api-recruiting-request.md)
- [Stanowisko wniosku o rekrutację](hr-admin-integration-ats-api-recruiting-request-position.md)
- [Umiejętność we wniosku o rekrutację](hr-admin-integration-ats-api-recruiting-request-skill.md)
- [Rekrutacja wymaga edukacji](hr-admin-integration-ats-api-recruiting-request-education.md)
- [Lokalizacja wniosku o rekrutację](hr-admin-integration-ats-api-recruiting-request-location.md)

Zestawy opcji:

- [Status zwolnienia z pracy](hr-admin-integration-ats-api-job-exempt-status.md)
- [Stan stanowiska dla wniosku o rekrutację](hr-admin-integration-ats-api-recruiting-request-position-status.md)
- [Stan wniosku o rekrutację](hr-admin-integration-ats-api-recruiting-request-status.md)
- [Kategoria stanowisk prawnych](hr-admin-integration-ats-api-regulatory-job-category.md)

## <a name="candidate-to-hire-and-related-entities-and-option-sets"></a>Kandydat do pracy oraz powiązane jednostki i zestawy opcji

Przykład kwerendy:

- [Przykład kwerendy dotyczącej kandydata do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)

Jednostki:

- [Kandydat do zatrudnienia](hr-admin-integration-ats-api-candidate-to-hire.md)
- [Osoba](hr-admin-integration-ats-api-person.md)
- [Wykształcenie osoby](hr-admin-integration-ats-api-person-education.md)
- [Doświadczenie zawodowe osoby](hr-admin-integration-ats-api-person-professional-experience.md)
- [Adres osoby](hr-admin-integration-ats-api-person-address.md)
- [Osoba kontaktowa strony](hr-admin-integration-ats-api-party-contact.md)
- [Kwalifikacje osoby](hr-admin-integration-ats-api-person-skill.md)
- [Poziom oceniania](hr-admin-integration-ats-api-rating-level.md)
- [Certyfikat osoby](hr-admin-integration-ats-api-person-certificate.md)
- [Typ certyfikatu](hr-admin-integration-ats-api-certificate-type.md)
- [Kontrola osoby](hr-admin-integration-ats-api-person-screening.md)
- [Typy kontroli](hr-admin-integration-ats-api-screening-types.md)
- [Numer dokumentu identyfikacyjnego osoby](hr-admin-integration-ats-api-person-identification-number.md)

Zestawy opcji:

- [Wynik integracji kandydata](hr-admin-integration-ats-api-applicant-integration-result.md)
- [Puste Tak Nie](hr-admin-integration-ats-api-blank-yes-no.md)
- [Stan ukończenia](hr-admin-integration-ats-api-completion-status.md)
- [Typ kontaktu](hr-admin-integration-ats-api-contact-type.md)
- [Podstawa kredytu edukacyjnego](hr-admin-integration-ats-api-education-credit-basis.md)
- [Rodzaj](hr-admin-integration-ats-api-gender.md)
- [Stan cywilny](hr-admin-integration-ats-api-marital-status.md)
- [Miesiące roku](hr-admin-integration-ats-api-months-of-year.md)
- [Nie, Tak](hr-admin-integration-ats-api-no-yes.md)
- [Jednostka okresu](hr-admin-integration-ats-api-period-unit.md)
- [Częstotliwość kontroli](hr-admin-integration-ats-api-screening-frequency.md)
- [Częstotliwość kontroli generowana na podstawie](hr-admin-integration-ats-api-screening-frequency-generate-from.md)
- [Typ poziomu kwalifikacji](hr-admin-integration-ats-api-skill-level-type.md)

## <a name="see-also"></a>Informacje dodatkowe

[Rekrutowanie kandydatów](hr-personnel-recruit.md)<br>
[Co to jest usługa Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)<br>
[Użyj interfejsu API sieci Web Microsoft Dataverse](/powerapps/developer/data-platform/webapi/overview)<br>
[Tworzenie i aktualizowanie zestawów opcji przy użyciu interfejsu API sieci Web](/powerapps/developer/data-platform/webapi/create-update-optionsets)<br>

[!INCLUDE[footer-include](../includes/footer-banner.md)]