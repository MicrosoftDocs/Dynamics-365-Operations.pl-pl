---
title: Konfigurowanie opcji uprawnień kontaktów osobistych
description: W programie Microsoft Dynamics 365 Human Resources można skonfigurować opcje uprawnień dla kontaktów osobistych. Kontakty osobiste mogą być beneficjentami lub osobami na utrzymaniu.
author: andreabichsel
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d85677973f67f0c68de6c5ede62c142524939833
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2021
ms.locfileid: "6054411"
---
# <a name="configure-personal-contact-eligibility-options"></a>Konfigurowanie opcji uprawnień kontaktów osobistych

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

W tym artykule przedstawiono sposób konfigurowania typów kontaktów osobistych do używania w świadczeniach w programie Microsoft Dynamics 365 Human Resources. Kontakty osobiste mogą być beneficjentami lub osobami na utrzymaniu. 

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
   | **Wiek** | Maksymalny wiek uprawnionego kontaktu osobistego w planie świadczeń. To pole jest aktywne tylko po wybraniu relacji. Ten wiek jest porównywany z obliczonym wiekiem kontaktu osobistego. Obliczony wiek to: (Data objęcia świadczeniem - data urodzenia kontaktu osobistego / 365) Ta liczba jest zawsze liczbą całkowitą. |

4. Wybierz opcję **Zapisz**. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]