# About Energy Storage Model

PH, May 2020


## Ideas

### Question

Is it true that *without* the complementarity consraints,
the optim problem

E+ = E + (Pcha - Pdis)Δt

is quite equivalent to the

E+ ≤ E + PΔt - P_loss(P)Δt ?

And what is the drawback of such formulation?

- we loose contro on a new power flow that we can call "supplementary losses" ?

let P_sup_loss = P - P_loss - (E+ - E)/Δt

then the energy storage dynamics inequality can be written as

P_sup_loss ≥ 0

### Fact
If P -> P_loss(P) is convex, then

E+ - E - PΔt + P_loss(P)Δt ≤ 0

is a convex constraint


### Application

*If* the consequences of dropping the equality constraint in favor of an inequality
are indeed none.

Then we could explore *non-linear but convex* losses models.

Example : P_losses = R(E, softsign(P)) * P²

Question, on what conditions on the R function is the P_losses function convex ?

Note: According to [DCP rules](https://dcp.stanford.edu/rules), it is cannot be found convex :-(


## In Shi 2019 ToAC - Battery control under cycling aging.pdf

Note here we may include a constraint that storage cannot charge and
discharge at the same time [40], but it turns out that this
condition will always be satisfied in our setting.

[40] M. R. Almassalkhi and I. A. Hiskens, “Model-predictive cascade mitiga-
tion in electric power systems with storage and renewablespart i: Theory
and implementation,” IEEE Transactions on Power Systems, vol. 30,
no. 1, pp. 67–77, 2015

## In Chen 2020 ToSG - Aggregate Power Flexibility.pdf

Equation in §II.B:

    E t = κ · E t−1 − Δt · P t

Remark 2: The DER models (4)-(7) are approximate for
the trade-off between model precision and computational efficiency.

Take the energy storage model (5) for example.
A more realistic model than (5) would have distinct charging
and discharging efficiencies, which would render the model
**nonconvex** and therefore hard to analyze and compute, due to
the complementarity constraint for charging and discharging power [23].

For computational efficiency, the simplified energy
storage model (5) is generally acceptable in practice [22]–[24].
Furthermore, the proposed power aggregation method is a
generic framework applicable to the cases with various DER
models that can be more detailed and realistic.

[22] M. Mahmoodi, P. Shamsi, and B. Fahimi, “Economic dispatch of a
hybrid microgrid with distributed energy storage,” IEEE Trans. Smart
Grid, vol. 6, no. 6, pp. 2607–2614, Nov. 2015.

[23] D. Zarrilli, A. Giannitrapani, S. Paoletti, and A. Vicino, “Energy stor-
age operation for voltage control in distribution networks: A receding
horizon approach,” IEEE Trans. Control Syst. Technol., vol. 26, no. 2,
pp. 599–609, Mar. 2018.

[24] N. Li, L. Chen, and S. H. Low, “Optimal demand response based on util-
ity maximization in power networks,” in Proc. IEEE PES Gen. Meeting,
San Diego, CA, USA, 2011, pp. 1–8.
