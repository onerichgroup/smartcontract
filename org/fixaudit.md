<h4>Maxsure Reward distribution not more than 11% / Year </h4>
 


<p>
<b style="color:orange">URI - Upline Reward Inflation</b><br>
Fixed = Update tokenomic<br>
Desc : Fixed to Max minting 11% / Year (10% staker + 1% upline)<br>
https://github.com/onerichgroup/smartcontract/blob/main/org/tokenomic.md
 <br>
</p>

<p>
<b style="color:orange">IRM - Incorrect Reward Mechanism</b><br>
Fixed = Update tokenomic and desc at withpaper<br>
Desc : With this distribution model , user must claim periodicaly , because after someone claim , reward pool will reducted , the more often you claim rewards, the rewards you get will be greater than those who claim rewards over a longer period.<br>
MaxReward : Use for set maximum APR if price ORG rise more than expected, with target APR 10-20% / Year , distribution of reward will lowwer than target maximum ( 100% ).
 <br>
</p>

<b style="color:orange">PCR - Potential Circular Referral</b><br>
Fixed = Code<br>
```sol
  require(Upline != msg.sender,"Upline invalid");
```
 <br>
</p>
<p>
<b style="color:orange">UMP - Unusual Minting Process</b>
Fixed = Code<br>
Desc = Have public bool minted[] for check<br>
```sol
mapping(uint256 => bool) public minted;
function mint(uint256 _id) public {
if(minted[_id]) return;//filter
}
```
 <br>
</p>

<p>
<b>MC - Missing Check</b><br>
Fixed : Code<br>
```sol
 require(pid <=5 ,"Invalid pid");
 ```
 <br>
</p>

<p>
<b>MC - Missing Check</b><br>
Fixed : Code<br>
```sol
 require(pid <=5 ,"Invalid pid");
 ```
 <br>
</p>






