---
title: Konfigurowanie opcji uprawnień do kontaktu osobistego
description: W tym artykule wyjaśniono sposób konfigurowania opcji uprawnień dla kontaktów osobistych w aplikacji Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/22/2022
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
ms.openlocfilehash: e3e393002901f31c035a54bd8036ed20ecdf9e00
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2022
ms.locfileid: "9803892"
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
   | **Wiek** |Określa maksymalny wiek osoby uprawnionej do kontaktu osobistego w ramach planu świadczeń. To pole jest aktywne tylko po wybraniu relacji. Ten wiek jest porównywany z obliczonym wiekiem kontaktu osobistego. Obliczony wiek to: (Data objęcia świadczeniem - data urodzenia kontaktu osobistego / 365) Ta liczba jest zawsze liczbą całkowitą.
W przypadku **Ośredniej osobistej zależnej** opcji kwalifikacji kontaktu wiek w tym polu jest wiekiem minimalnym. Na przykład: jeśli wiek jest ustawiony na 18 lat w opcji **Odpowiednia zależność**, osoby zależne, które są oznaczone jako nadliczbowe zależne i mają 18 lat lub więcej, byłyby objęte opcją kwalifikującą.  |

4. Wybierz opcję **Zapisz**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
