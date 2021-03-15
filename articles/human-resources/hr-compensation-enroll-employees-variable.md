---
title: Zarejestrowanie pracownika w systemie wynagrodzeń o zmiennej wysokości
description: Menedżer ds. wynagrodzenia i świadczeń może rejestrować pracowników w planach wynagrodzeń o zmiennej wysokości w celu obliczania dla nich nagród pieniężnych i niepieniężnych.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMCompVarEnrollEmpl, HcmCompensationWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a7a173403e79212be5e4aac36d99f349da159e08
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/03/2021
ms.locfileid: "5113862"
---
# <a name="enroll-an-employee-in-a-variable-compensation-plan"></a>Zarejestrowanie pracownika w systemie wynagrodzeń o zmiennej wysokości

Menedżer ds. wynagrodzenia i świadczeń może rejestrować pracowników w planach wynagrodzeń o zmiennej wysokości w celu obliczania dla nich nagród pieniężnych i niepieniężnych. Ta procedura zakłada, że plan wynagrodzeń o zmiennej wysokości został utworzony z polem Włącz rejestrację ustawionym na wartość Tak, a dla tego planu utworzono reguły uprawnienia. Dane wykorzystane do stworzenia tej procedury pochodzą z firmy demonstracyjnej USMF. Aby rozpocząć procedurę, wybierz kolejno opcje Zasoby ludzkie > Pracownicy > Pracownicy > Wynagrodzenie > Rejestracja w planie o zmiennej wysokości.

1. Kliknij przycisk Nowy.
2. W polu Plan kliknij przycisk rozwijany, aby otworzyć wyszukiwanie.
    * Wyszukiwanie planu zostanie wyfiltrowane w celu wyświetlenia tylko planów wynagrodzeń o zmiennej wysokości, do których pracownik jest uprawniony zgodnie z regułami uprawnień.  
3. Na liście kliknij łącze w wybranym wierszu.
4. Przełącz rozwinięcie sekcji Ogólne.
5. W polu Data obowiązywania wprowadź datę.
6. Kliknij przycisk Zapisz.
7. Przełącz rozwinięcie sekcji Zastąpienia.
    * Opcjonalnie można ustawić datę reguły zatrudnienia, aby zastępować datę zatrudnienia pracownika, gdy regułą zatrudnienia określoną dla wybranego planu jest Procent.  
    * Jeśli plan wynagrodzeń o zmiennej wysokości opiera się na procencie podstawy, można zastąpić wartość procentową nagrody dla pracownika. Jeśli plan wynagrodzeń o zmiennej wysokości opiera się na liczbie jednostek, można zastąpić liczbę jednostek dla pracownika.  
    * Jeśli pracownik powinien otrzymać stałą kwotę nagrody, kwotę można ustawić w tym miejscu.  
8. Przełącz rozwinięcie sekcji Zastąpienia na poziomie organizacji.
    * Jeśli należy wziąć pod uwagę wyniki osiągane przez pracownika, różne działy lub dział inny niż przypisany w stanowisku pracownika, można zastąpić dział. Wartość w kolumnie Procent musi mieć łącznie 100.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]