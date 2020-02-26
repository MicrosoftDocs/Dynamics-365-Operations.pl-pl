---
title: Ustawianie parametrów obszaru roboczego Zarządzanie świadczeniami
description: Tu opisano konfigurowanie parametrów obszaru roboczego Zarządzanie świadczeniami dostępnego w programie Microsoft Dynamics 365 Human Resources.
author: andreabichsel
manager: AnnBe
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
ms.openlocfilehash: ab9b1fc78ce42479d9265b80337adf899cec3866
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2020
ms.locfileid: "3010211"
---
# <a name="set-benefits-management-parameters"></a>Ustawianie parametrów obszaru roboczego Zarządzanie świadczeniami

[!include [banner](includes/preview-feature.md)]

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
   | **Rozszerzenie rocznego wynagrodzenia** | Określa, czy ma być automatycznie obliczana kwota w polu **Roczne wynagrodzenie z tytułu świadczenia** w oknie **Szczegóły świadczeń pracowniczych**. Bazuje ona na ustawieniach **Stawka płacy stałego wynagrodzenia**, **Średnia liczba godzin** i **Częstotliwość płatności** dotyczących pracownika.</br></br>**Średnia liczba godzin** x **Stała stawka płacy** x **Częstotliwość płatności** (liczba okresów płacowych) = **Roczne wynagrodzenie z tytułu świadczenia** </br></br>Jeśli którakolwiek z wartości w polach **Średnia liczba godzin**, **Stawka płacy stałego wynagrodzenia** lub **Częstotliwość płatności** ulegnie zmianie, system automatycznie przeliczy kwotę **Roczne wynagrodzenie z tytułu świadczenia** na podstawie zmienionych wartości. System utworzy rekord **Data wejścia w życie** w celu zidentyfikowania dokładnej daty i godziny wystąpienia zmiany. W razie potrzeby można ręcznie edytować ilość w polu **Roczne wynagrodzenie z tytułu świadczenia**. |
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
