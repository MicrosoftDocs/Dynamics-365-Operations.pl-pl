---
title: Konfigurowanie parametrów zarządzania świadczeniami i samoobsługi pracownika etatowego dla wszystkich firm
description: Konfigurowanie parametrów zarządzania świadczeniami i samoobsługi pracownika etatowego w Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 5e241475c9652ab2dafe6886479e9c0a93711aca
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/17/2021
ms.locfileid: "5466767"
---
# <a name="set-benefits-management-and-employee-self-service-parameters-for-all-companies"></a>Konfigurowanie parametrów zarządzania świadczeniami i samoobsługi pracownika etatowego dla wszystkich firm

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Zanim będzie można konfigurować plany świadczeń w module Microsoft Dynamics 365 Human Resources, należy skonfigurować parametry obszaru roboczego Zarządzanie świadczeniami. Te parametry służą do ustawiania wartości domyślnych, kodów przyczyny i innych opcji. 

## <a name="configure-general-parameters"></a>Konfigurowanie parametrów ogólnych

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Udostępniane parametry Human Resources**.

2. Na karcie **Zarządzanie świadczeniami** wprowadź wartości w następujących polach:

   | Pole | opis |
   | --- | --- |
   | **Kraj/region** | Pole **Kraj/region** określa kolejność wyświetlania kodów pocztowych/jednostek administracyjnych. Wybrany kraj jest wyświetlany jako pierwszy na liście rozwijanej. |
   | **Kod przyczyny rejestracji** | Umożliwia wybór domyślnego kodu przyczyny, który będzie używany podczas tworzenia planów dla pracowników etatowych w trakcie przetwarzania otwartej rejestracji. |
   | **Kod powodu anulowania** | Kod przyczyny, który ma być używany podczas anulowania planu świadczeń pracowniczych. Jest wyświetlany w oknie dialogowym podczas procesu anulowania. W razie potrzeby użytkownicy mogą go zmienić w polu **Kody powodu anulowania**. |
   | **Kod przyczyny ponownego otwarcia** | Kod przyczyny, który ma być używany podczas ponownego otwarcia planu świadczeń pracowniczych. Jest wyświetlany w oknie dialogowym podczas procesu anulowania. W razie potrzeby użytkownicy mogą go zmienić w polu **Kody przyczyny ponownego otwarcia**. | 
   | **Kod przyczyny zdarzenia zmiany sytuacji życiowej** | Kod przyczyny, który ma być używany w razie zmiany sytuacji życiowej. |
   | **Kod przyczyny zmiany stawki** | Kod przyczyny, który ma być używany podczas anulowania i ponownego otwierania planu świadczeń pracowniczych w trakcie procesu aktualizacji zmiany stawki. Wskazuje, które rekordy zostały zmienione przez proces aktualizacji zmiany stawki. |
   | **Roczne wynagrodzenie z tytułu świadczenia** | Umożliwia ustawienie kwoty **Świadczenia do wynagrodzenia rocznego** dla pracownika. Przy ustalaniu kwot pokrycia w Human Resources zamiast kwoty rocznej dla stałej płacy będzie używana kwota **Świadczenia do wynagrodzenia rocznego**. |
   | **Nowo zatrudniona osoba kwalifikuje się** | Określa, czy nowo zatrudnione osoby kwalifikują się do planu. |
   | **Okres rejestracji nowo zatrudnionej osoby** | Okres, w którym jest dozwolone rejestrowanie nowo zatrudnionej osoby.</br></br>**Uwaga**: to ustawienie zastępuje każdy okres rejestracji nowo zatrudnionej osoby ustawiony w regule uprawnienia do planu. |
   | **Domyślna częstotliwość wypłat** | Domyślna częstotliwość płac, która ma być używana przy dodawaniu nowych pracowników. |
   | **Zdarzenia zmiany sytuacji życiowej zostały włączone** | Włącza obsługę zmian sytuacji życiowej. |
   | **Ukryj starsze formularze świadczeń** | Umożliwia ukrycie starszych formularzy świadczeń. |
   | **Weryfikacja świadczenia** | Tekst weryfikacyjny używany podczas realizacji świadczeń w samoobsłudze. |
   | **Automatyczny wybór osób wyznaczonych** | Określa, czy osoby na utrzymaniu i beneficjenci mają być automatycznie wybierani na podstawie ich uprawnień do opcji planu. |

3. Wybierz opcję **Zapisz**.

## <a name="configure-employee-self-service-parameters"></a>Konfigurowanie parametrów obszaru Samoobsługa pracownika etatowego

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry Human Resources**.

2. Na karcie **Zarządzanie świadczeniami** wprowadź wartości w następujących polach:

   | Pole | opis |
   | --- | --- |
   | **Weryfikacja świadczenia** | Tekst weryfikacyjny używany podczas realizacji świadczeń w samoobsłudze. |
   | **Automatyczny wybór osób wyznaczonych** | Określa, czy osoby na utrzymaniu i beneficjenci mają być automatycznie wybierane na podstawie ich uprawnień do opcji planu. |

3. Wybierz opcję **Zapisz**.




[!INCLUDE[footer-include](../includes/footer-banner.md)]