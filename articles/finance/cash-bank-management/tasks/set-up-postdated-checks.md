---
title: Konfigurowanie czeków postdatowanych
description: W tym artykule wyjaśniono, jak można określić, czy należy księgować zapisy arkusza dla postdatowanych czeków i których arkuszy księgowania należy użyć do wyczyszczenia wpisów i płatności dostawcy.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: BankParameters, VendPaymMode, CustPaymMode
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: a5ef9aa6b67eb630713dd1f15b2ae49c358edae9
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2022
ms.locfileid: "9804190"
---
# <a name="set-up-postdated-checks"></a>Konfigurowanie czeków postdatowanych

[!include [banner](../../includes/banner.md)]

W tym artykule wyjaśniono, jak można określić, czy należy księgować zapisy arkusza dla postdatowanych czeków i których arkuszy księgowania należy użyć do wyczyszczenia wpisów i płatności dostawcy. Można także określić konta rozliczeniowe dla czeków wystawionych, czeków otrzymanych i potrąconej zaliczki na podatek. Czeki postdatowane są wystawiane do celów wykonywania i odbierania płatności w przyszłości. Można określić, czy czek ma być widoczny w księgach rachunkowych przed jego terminem płatności.



Rolą w tej procedurze jest Skarbnik. Ta procedura wykorzystuje firmę demonstracyjną USMF.


## <a name="set-up-postdated-checks"></a>Konfigurowanie czeków postdatowanych
1. Wybierz kolejno opcje **Zarządzanie gotówką i bankami > Ustawienia > Parametry modułu Zarządzanie gotówką i bankami**.
2. Kliknij kartę **Czeki postdatowane**.
3. Zaznacz lub wyczyść pole wyboru **Włącz czeki postdatowane**.
4. Zaznacz lub wyczyść pole wyboru **Księguj arkusze finansowe dla czeków postdatowanych**.
5. W polu **Konto rozrachunkowe dla czeków wystawionych** określ żądane wartości.
6. W polu **Konto rozrachunkowe dla czeków otrzymanych** określ żądane wartości.
7. W polu **Arkusz finansowy dla wpisów rozrachunkowych** wpisz wartość.
8. W polu **Prześlij czeki postdatowane do tego arkusza płatności dostawcy** wpisz wartość.
9. W polu **Konto rozrachunkowe potrąconej zaliczki na podatek** określ żądane wartości.
10. Kliknij przycisk **Zapisz**.
11. Zamknij stronę.
12. Wybierz kolejno opcje **Rozrachunki z dostawcami > Ustawienia płatności > Metody płatności**.
13. Kliknij przycisk **Nowy**.
14. W polu **Metoda płatności** wpisz wartość.
15. Zaznacz opcję **Księgowanie rozrachunkowe czeków postdatowanych**, aby wskazać, że kwota czeku ma być księgowana na koncie rozliczeniowym.
16. W polu **Typ konta** wybierz opcję **Bank**.
    * Kontem przeciwstawnym w metodzie płatności będzie konto bankowe.  
17. W polu **Konto płatności** podaj żądane wartości.
    * Wybierz konto bankowe, które jest używane do odliczenia kwoty faktury.  
18. Kliknij przycisk **Zapisz**.
19. Zamknij stronę.
> [!NOTE]
> Aby mieć możliwość księgowania czeku postdatowego na koncie bankowym, gdy data sesji jest nie wcześniejsza niż termin płatności, należy włączyć funkcję **Weryfikacji terminów płatności arkusza księgowania płatności z czekami postdatowanych na koncie bankowym**. Ta funkcja umożliwia księgować arkusze płatności dla dostawców lub odbiorców z czekami postdatywami, jeśli data sesji nie jest wcześniejsza niż termin płatności.
> 
> Podczas ustawiania **Metody płatności** (**Rozrachunki z dostawcami > Ustawienia płatności > Metody płatności**) nie należy wypełniać **konta pomostowego**. W tym przypadku konto przeciwstawne jest wypełniane kontem bankowym ustawionym w formularzu **Metoda płatności**.
>  
> Gdy funkcja jest włączona, a data sesji jest wcześniejsza niż data zapadalności, podczas księgowania arkusza płatności wyświetlany jest następujący komunikat o błędzie: **Data zapadalności musi być mniejsza lub równa dacie sesji, jeśli typ konta przeciwstawnego to Bank**. Jeśli funkcja nie jest włączona, można zaksięgować arkusz płatności z postdatowanym czekiem, gdy data sesji jest wcześniejsza niż data zapadalności.
> Ta funkcja jest włączana w wersji 10.0.21 i nowsze.    

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
