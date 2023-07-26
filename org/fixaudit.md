<h4>Maxsure Reward distribution not more than 11% / Year </h4>
 


<p>
<b style="color:orange">URI - Upline Reward Inflation</b></br>
Fixed = Update tokenomic</br>
Desc : Fixed to Max minting 11% / Year (10% staker + 1% upline)</br>
https://github.com/onerichgroup/smartcontract/blob/main/org/tokenomic.md
 </br>
</p>

<p>
<b style="color:orange">IRM - Incorrect Reward Mechanism</b></br>
Fixed = Update tokenomic and desc at withpaper</br>
Desc : With this distribution model , user must claim periodicaly , because after someone claim , reward pool will reducted , the more often you claim rewards, the rewards you get will be greater than those who claim rewards over a longer period.</br>
MaxReward : Use for set maximum APR if price ORG rise more than expected, with target APR 10-20% / Year , distribution of reward will lowwer than target maximum ( 100% ).
 </br>
</p>

<b style="color:orange">PCR - Potential Circular Referral</b></br>
Fixed = Code</br>

```
  require(Upline != msg.sender,"Upline invalid");

```
 </br>
</p>

<p>
<b style="color:orange">UMP - Unusual Minting Process</b><br>
Fixed = Code</br>
Desc = Have public bool minted[] for check</br>

```
mapping(uint256 => bool) public minted;
function mint(uint256 _id) public {
if(minted[_id]) return;//filter
}

```
 </br>
</p>

<p>
<b>MC - Missing Check</b></br>
Fixed : Code</br>

```
require(pid <=5 ,"Invalid pid");

```
 </br>
</p>

<p>

<b>SCD - Supply Configuration Discrepancy</b></br>
Fixed : Code</br>

```
uint256 public unMint = 2e24;

 _limit_mint(msg.sender, 2e23); //initial mint

```
 </br>
</p>



<p>

<b>RAU - Redundant Array Usage</b></br>
Fixed : Code</br>

```

uint256[] public config_timelock=[7890000,15780000,31560000,47340000,63120000,94680000]; //3,6,12,18,24,36 months

```
 </br>
</p>



<p>

<b>CR - Code Repetition</b></br>
Fixed : Code</br>
Desc : Option emergency on unstake function , and remove emergency function<br>

```

 function unstake(uint256 tokenId ,bool is_emergency) public {
        require(tokenId>0,"Require tokenId");
        if(!is_emergency){
        claim_staking_reward(tokenId);
        }

```
 </br>
</p>

<p>

<b> TUU - Time Units Usage</b></br>
Fixed : Code</br>
 
```

uint256 public secondperyears = 31560000;

```
 </br>
</p>

<p>

<b>MEE - Missing Events Emission</b></br>
Fixed : Code</br>
 
```

    event Stake(address addr, address nft , uint256 tokenId, uint256 pid);
    event Unstake(address addr, address nft , uint256 tokenId, uint256 pid);
    event Claim(address addr, uint256 tokenId, uint256 amount);
    event Affiliate(address addr, uint256 tokenId, uint256 amount);
    event SendToDefi(uint256 time, uint256 amount);
    
    

```
 </br>
</p>

<p>
<b>RSML - Redundant SafeMath Library</b></br>
Fixed : Code</br>
Desc : remove library and change math to normal math
 
 </br>
</p>


<p>
<b>RSK - Redundant Storage Keyword</b></br>
Fixed : Code</br>
Desc : remove storage at view function
 
 </br>
</p>


<p>
<b>IDI - Immutable Declaration Improvement</b></br>
Fixed : Code</br>
Desc : <br>
 config_timelock = has been remove from construct
 max_reward_persecond = dev able to reconfig to ajust / custom APR 

 </br>
</p>


<p>

<b>L02 - State Variables could be Declared Constant
</b></br>
Fixed : Code</br>
 
```

    uint256[] public max_reward_persecond;
    uint256[] public config_timelock=[7890000,15780000,31560000,47340000,63120000,94680000]; //3,6,12,18,24,36 months
    uint256 constant public config_referral_percent = 10;
    uint256 public unMint = 2e24;
    uint256 public LastUseDeFi;
    uint256 constant public YearlyDistributionDeFi = 5;
    uint256 constant public YearlyDistributionStaking = 5;
    uint256 constant public secondperyears = 31560000;
    address public DeFiContract;
    bool    public DeFiIsFix = false;

```
 </br>
</p>


<p>

<b>L11 - Unnecessary Boolean equality
</b></br>
Fixed : Code</br>
 
```

 require(!DeFiIsFix,"Unable to change DeFi contract");

```
 </br>
</p>



<p>

<b>L13 - Divide before Multiply Operation
</b></br>
Fixed : Desc</br>
Desc: This is sub not div
```

uint256 diverent = block.timestamp.sub(LastUseDeFi).mul(persecond)

```
</br>
</p>


<p>

<b>L16 - Validate Variable Setters
</b></br>
Fixed : Code</br>
 
```

    // unable to change contract after fix
    function setContract(address defi) public onlyOwner {
         require(!DeFiIsFix,"Unable to change DeFi contract");
         require(defi != address(0),"Unable to change DeFi contract");
         DeFiContract = defi;
    }

    // onetime setup , unable to undo
    function SetFixDefi() public onlyOwner { 
         require(DeFiContract != address(0),"Unable to change DeFi contract");
         DeFiIsFix = true;
    }
 
```
</br>
</p>


<b>L16 - Validate Variable Setters
</b></br>
Fixed : Code</br>
 
```

 
 
```
</br>
</p>

