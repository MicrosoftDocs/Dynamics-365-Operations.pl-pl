---
title: Konfigurowanie opcji uprawnień do kontaktu osobistego
description: W tym artykule wyjaśniono sposób konfigurowania opcji uprawnień dla kontaktów osobistych w aplikacji Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/24/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 251a12b0da364744f1d8c84324099708a2f816a1
ms.sourcegitcommit: 1717ff6af1879c6f3a8360936c42ecf55f86acd0
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/07/2022
ms.locfileid: "9749290"
---
# <a name="configure-personal-contact-eligibility-options"></a>Konfigurowanie opcji uprawnień do kontaktu osobistego


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule wyjaśniono, jak skonfigurować typy kontaktów osobistych, które mogą być używane w korzyściach w Microsoft Dynamics 365 Human Resources. Kontakty osobiste to osoby, które będą objęte Twoimi planami (osoby na utrzymaniu) lub które skorzystają z Twoich planów (beneficjenci). Osoby na utrzymaniu to zazwyczaj małżonkowie lub dzieci. Beneficjentami mogą być małżonkowie, dzieci, osoby podlegające lub rodzice.

1. W obszarze roboczym **Zarządzanie świadczeniami** w sekcji **Konfiguracja** wybierz opcję **Opcje uprawnień kontaktów osobistych**.

2. Wybierz pozycję **Nowy**.

3. Określ wartości dla następujących pól:

   | Pole | Opis |
   | --- | --- |
   | **Opcja uprawnienia** | Unikatowa nazwa lub kod opcji uprawienia służący do identyfikacji opcji uprawnienia. |
   | **Opis** | Krótki opis opcji uprawnienia. |
   | **Kod uprawnienia osoby kontaktowej** | Kod systemowy, który najlepiej opisuje opcję osobistego uprawnienia. Dostępne są następujące opcje: <ul><li>Pokrewieństwo</li><li>Uczeń lub student</li><li>Osoba na utrzymaniu przekraczająca granicę wieku</li><li>Niepełnosprawna osoba na utrzymaniu przekraczająca granicę wieku</li></ul> |
   | **Stan** | Stan opcji uprawnienia. Jeśli stan opcji uprawnienia jest ustawiony jako nieaktywny, nie można wybierać tej opcji uprawnienia kontaktu osobistego dla kontaktów osobistych. |
   | **Pokrewieństwo** | Określa relację między kontaktem osobistym a pracownikiem etatowym. To pole jest aktywne tylko wtedy, gdy kod uprawnienia kontaktu jest ustawiony jako Relacja. |
   | **Wiek** | Minimalny wiek uprawnionego kontaktu osobistego w planie świadczeń. To pole jest aktywne tylko po wybraniu relacji. Ten wiek jest porównywany z obliczonym wiekiem kontaktu osobistego. Obliczony wiek to: (Data objęcia świadczeniem - data urodzenia kontaktu osobistego / 365) Ta liczba jest zawsze liczbą całkowitą. |

4. Wybierz opcję **Zapisz**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
