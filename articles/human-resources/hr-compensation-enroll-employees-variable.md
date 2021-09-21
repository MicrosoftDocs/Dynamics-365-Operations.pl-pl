---
title: Zarejestrowanie pracownika w systemie wynagrodzeń o zmiennej wysokości
description: Menedżer ds. wynagrodzenia i świadczeń może rejestrować pracowników w planach wynagrodzeń o zmiennej wysokości w celu obliczania dla nich nagród pieniężnych i niepieniężnych.
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 67b3cd95276b9e59e794583fa51ddbcec4c43b1e
ms.sourcegitcommit: a8ac6d9b63eb67d14dd17a086ef4f1eccd7f9fc1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/27/2021
ms.locfileid: "7431321"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a>Zarejestrowanie pracownika w systemie wynagrodzeń o zmiennej wysokości

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Menedżer ds. wynagrodzenia i świadczeń może rejestrować pracowników w planach wynagrodzeń o zmiennej wysokości w celu obliczania dla nich nagród pieniężnych i niepieniężnych. Ta procedura zakłada, że plan wynagrodzeń o zmiennej wysokości został utworzony z polem **Włącz rejestrację** ustawionym na wartość Tak, a dla tego planu utworzono reguły uprawnienia. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Aby rozpocząć procedurę, wybierz kolejno opcje **Zasoby ludzkie** > **Pracownicy** > **Pracownicy etatowi** > **Wynagrodzenie** > **Rejestracja w planie o zmiennej wysokości**.

1. Kliknij przycisk **Nowy**.
2. W polu **Plan** kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wyszukiwanie planu zostanie wyfiltrowane w celu wyświetlenia tylko planów wynagrodzeń o zmiennej wysokości, do których pracownik jest uprawniony zgodnie z regułami uprawnień.  
3. Na liście kliknij łącze w wybranym wierszu.
4. Przełącz rozwinięcie sekcji Ogólne.
5. W polu **Data wejścia w życie** wprowadź datę.
6. Kliknij przycisk **Zapisz**.
7. Przełącz rozwinięcie sekcji **Zastąpienia**.
    * Opcjonalnie można ustawić datę reguły zatrudnienia, aby zastępować datę zatrudnienia pracownika, gdy regułą zatrudnienia określoną dla wybranego planu jest Procent.  
    * Jeśli plan wynagrodzeń o zmiennej wysokości opiera się na procencie podstawy, można zastąpić wartość procentową nagrody dla pracownika. Jeśli plan wynagrodzeń o zmiennej wysokości opiera się na liczbie jednostek, można zastąpić liczbę jednostek dla pracownika.  
    * Jeśli pracownik powinien otrzymać stałą kwotę nagrody, kwotę można ustawić w tym miejscu.  
8. Przełącz rozwinięcie sekcji **Zastąpienia na poziomie organizacji**.
    * Jeśli należy wziąć pod uwagę wyniki osiągane przez pracownika, różne działy lub dział inny niż przypisany w stanowisku pracownika, można zastąpić dział. Wartość w kolumnie **Procent** musi mieć łącznie 100.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
