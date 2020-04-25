---
title: Ustawianie parametrów obszaru roboczego Zarządzanie świadczeniami
description: Tu opisano konfigurowanie parametrów obszaru roboczego Zarządzanie świadczeniami dostępnego w programie Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
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
ms.openlocfilehash: 9d6d463df08b9ae68047f09316f19e98740a8441
ms.sourcegitcommit: a9461650d11d6845e1942865ebf7e35f75f61ad3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/06/2020
ms.locfileid: "3229770"
---
# <a name="set-benefits-management-parameters"></a>Ustawianie parametrów zarządzania świadczeniami

Zanim będzie można konfigurować plany urlopów w module Microsoft Dynamics 365 Human Resources, należy skonfigurować parametry obszaru roboczego Zarządzanie świadczeniami. Te parametry służą do ustawiania wartości domyślnych, kodów przyczyny i innych opcji.

## <a name="configure-general-parameters"></a>Konfigurowanie parametrów ogólnych

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry**.

2. Na karcie **Ogólne** wprowadź wartości w następujących polach:

   | Pole | Opis |
   | --- | --- |
   | **Kraj/region** | Pole **Kraj/region** określa kolejność wyświetlania kodów pocztowych/jednostek administracyjnych. Wybrany kraj jest wyświetlany jako pierwszy na liście rozwijanej. |
   | **Kod przyczyny rejestracji** | Umożliwia wybór domyślnego kodu przyczyny, który będzie używany podczas tworzenia planów dla pracowników etatowych w trakcie przetwarzania otwartej rejestracji. |
   | **Kod powodu anulowania** | Kod przyczyny, który ma być używany podczas anulowania planu świadczeń pracowniczych. Jest wyświetlany w oknie dialogowym podczas procesu anulowania. W razie potrzeby użytkownicy mogą go zmienić w polu **Kody powodu anulowania**. |
   | **Kod przyczyny ponownego otwarcia** | Kod przyczyny, który ma być używany podczas ponownego otwarcia planu świadczeń pracowniczych. Jest wyświetlany w oknie dialogowym podczas procesu anulowania. W razie potrzeby użytkownicy mogą go zmienić w polu **Kody przyczyny ponownego otwarcia**. | 
   | **Kod przyczyny zdarzenia zmiany sytuacji życiowej** | Kod przyczyny, który ma być używany w razie zmiany sytuacji życiowej. |
   | **Kod przyczyny zmiany stawki** | Kod przyczyny, który ma być używany podczas anulowania i ponownego otwierania planu świadczeń pracowniczych w trakcie procesu aktualizacji zmiany stawki. Wskazuje, które rekordy zostały zmienione przez proces aktualizacji zmiany stawki. |
   | **Nowo zatrudniona osoba kwalifikuje się** | Określa, czy nowo zatrudnione osoby kwalifikują się do planu. |
   | **Okres rejestracji nowo zatrudnionej osoby** | Okres, w którym jest dozwolone rejestrowanie nowo zatrudnionej osoby.</br></br>**Uwaga**: to ustawienie zastępuje każdy okres rejestracji nowo zatrudnionej osoby ustawiony w regule uprawnienia do planu. | 
   | **Zdarzenia zmiany sytuacji życiowej zostały włączone** | Włącza obsługę zmian sytuacji życiowej. |
   | **Ukryj starsze formularze świadczeń** | Umożliwia ukrycie starszych formularzy świadczeń. |

3. Wybierz opcję **Zapisz**.

## <a name="configure-employee-self-service-parameters"></a>Konfigurowanie parametrów obszaru Samoobsługa pracownika etatowego

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Parametry**.

2. Na karcie **Samoobsługa pracownika etatowego** wprowadź wartości w następujących polach:

   | Pole | Opis |
   | --- | --- |
   | **Weryfikacja świadczenia** | Tekst weryfikacyjny używany podczas realizacji świadczeń w samoobsłudze. |
   | **Automatyczny wybór osób wyznaczonych** | Określa, czy osoby na utrzymaniu i beneficjenci mają być automatycznie wybierane na podstawie ich uprawnień do opcji planu. |

3. Wybierz opcję **Zapisz**.
